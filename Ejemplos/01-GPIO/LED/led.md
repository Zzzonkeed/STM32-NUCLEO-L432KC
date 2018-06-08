
En este ejemplo se programaron 3 LED con los pines PA_8, PA_9 y PA_10, los cuales se encienden en secuencia.

````C
  int main(void){
  /* USER CODE BEGIN 1 */

  /* USER CODE END 1 */

  /* MCU Configuration----------------------------------------------------------*/

  /* Reset of all peripherals, Initializes the Flash interface and the Systick. */
  HAL_Init();

  /* USER CODE BEGIN Init */

  /* USER CODE END Init */

  /* Configure the system clock */
  SystemClock_Config();

  /* USER CODE BEGIN SysInit */

  /* USER CODE END SysInit */

  /* Initialize all configured peripherals */
  MX_GPIO_Init();
  MX_USART2_UART_Init();
  /* USER CODE BEGIN 2 */

  /* USER CODE END 2 */

  /* Infinite loop */
  /* USER CODE BEGIN WHILE */
  while (1){

  /* USER CODE END WHILE */
	  HAL_GPIO_WritePin(LED1_GPIO_Port,LED1_Pin,1);
	  HAL_GPIO_WritePin(GPIOA,LED2_Pin,1); //PA_8
	  HAL_GPIO_WritePin(GPIOA,LED3_Pin,0); //PA_9
	  HAL_GPIO_WritePin(GPIOA,LED4_Pin,0); //PA_10
	  HAL_Delay(500);
	  HAL_GPIO_WritePin(GPIOA,LED2_Pin,0);
	  HAL_GPIO_WritePin(GPIOA,LED3_Pin,1);
	  HAL_GPIO_WritePin(GPIOA,LED4_Pin,0);
	  HAL_Delay(500);
	  HAL_GPIO_WritePin(GPIOA,LED2_Pin,0);
	  HAL_GPIO_WritePin(GPIOA,LED3_Pin,0);
	  HAL_GPIO_WritePin(GPIOA,LED4_Pin,1);
	  HAL_Delay(500);
  /* USER CODE BEGIN 3 */
  }
  /* USER CODE END 3 */

}
````

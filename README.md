import pandas as pd
import numpy as np
# Создание искусственного датасета
np.random.seed(0)
n_samples = 1000
# Признаки
transaction_amount = np.random.uniform(10, 10000, n_samples)
location = np.random.choice(['Local', 'Domestic', 'International'], n_samples)
time_of_day = np.random.choice(['Morning', 'Afternoon', 'Evening', 'Night'], n_samples)
transaction_category = np.random.choice(['Purchase', 'Withdrawal', 'Transfer'], n_samples)
transaction_frequency = np.random.randint(1, 10, n_samples)
transaction_history = np.random.randint(1, 11, n_samples)
# Создание флага фрода (0 - безопасная транзакция, 1 - фродовая транзакция)
fraud_flag = np.random.choice([0, 1], n_samples, p=[0.9, 0.1])
# Создание DataFrame
data = pd.DataFrame({
    'TransactionAmount': transaction_amount,
    'Location': location,
    'TimeOfDay': time_of_day,
    'TransactionCategory': transaction_category,
    'TransactionFrequency': transaction_frequency,
    'TransactionHistory': transaction_history,
    'FraudFlag': fraud_flag
})
# Вывод первых пяти строк датасета
print(data.head())
# Сохранение датасета в CSV-файл
data.to_csv('bank_fraud_dataset.csv', index=False)

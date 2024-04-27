# Docker-команда FROM вказує базовий образ контейнера
# Наш базовий образ - це Linux з попередньо встановленим python-3.10
FROM python:3.12.2

# Встановимо змінну середовища
ENV APP_HOME /app

# Install system dependencies
#RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

RUN pip install 'poetry==1.8.2'

# Install Poetry
#RUN curl -sSL https://install.python-poetry.org | python -

# Встановимо робочу директорію всередині контейнера
WORKDIR $APP_HOME

# Copy the poetry files
COPY pyproject.toml poetry.lock ./

# Встановимо залежності всередині контейнера
RUN poetry install 

# Скопіюємо інші файли в робочу директорію контейнера
COPY . .

# Позначимо порт, де працює застосунок всередині контейнера
EXPOSE 5000

# Запустимо наш застосунок всередині контейнера
ENTRYPOINT ["python", "main.py"]
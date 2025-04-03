
import logging
from aiogram import Bot, Dispatcher, types
from aiogram.types import ParseMode
from aiogram.contrib.middlewares.logging import LoggingMiddleware
from aiogram.utils import executor
from dotenv import load_dotenv
import os

# Завантажуємо змінні середовища з .env файлу
load_dotenv()

# Отримуємо токен з .env
API_TOKEN = os.getenv("TELEGRAM_TOKEN")

# Налаштування логування
logging.basicConfig(level=logging.INFO)

# Створення екземплярів бота та диспетчера
bot = Bot(token=API_TOKEN)
dp = Dispatcher(bot)
dp.middleware.setup(LoggingMiddleware())

# Команда старт
@dp.message_handler(commands=['start'])
async def welcome(message: types.Message):
    await message.reply("Привіт! Я бот для програми лояльності фотографів.")

if __name__ == '__main__':
    from aiogram import executor
    executor.start_polling(dp, skip_updates=True)


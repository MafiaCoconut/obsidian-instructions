Основная часть бота
```python
from aiogram import Dispatcher

dp = Dispatcher()
bot = Bot(TOKEN, parse_mode=ParseMode.HTML)

async def main() -> None:
	await dp.start_polling(bot)

if __name__ == "__main__":  
	asyncio.run(main())
```

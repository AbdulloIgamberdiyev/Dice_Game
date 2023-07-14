# Dice_Game
Dice game inTgBot

    @dp.message_handler(text="/dice")
    async def cmd_dice(message: types.Message):
        await message.answer("First it`s my turn!")
        await sleep(0.2)
        bot_data = await message.answer_dice()
        await sleep(5)
        await message.answer("Now it`s your turn!")
        await sleep(0.2)
        bot_data = bot_data['dice']['value']
        user_data = await message.answer_dice('🎲')
        await sleep(5)
        user_data = user_data['dice']['value']
        if user_data > bot_data:
            await message.answer("You win😄")
        elif user_data == bot_data:
            await message.answer('DRAW!🤝')
        else:
            await message.answer("You lose😢")

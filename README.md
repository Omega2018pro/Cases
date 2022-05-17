import discord
import random
from config_for_GigaBot import settings


s = 0
common_case = [0, 0, 0, 0, 1, 1, 1, 2, 2, 5]
all_case = [0, 0, 0, 0, 0, 0, 0, 0, 0, 10]
chip_case = [0, 0, 0, 0, 1, 1, 1, 1, 2, 2] 
big_case = [0, 0, 0, 0, 1, 1, 2, 2, 5, 10] 
gold_case = [0, 0, 0, 0, 1, 1, 2, 2, 5, 10]
blitz_case = [0, 0, 0, 0, 0, 1, 2, 2, 5, 10]


class MyClient(discord.Client):
    async def on_ready(self):
        print('Logged on ass', self.user)

    async def on_message(self, message):
        # don't respond to ourselves
        if message.author == self.user:
            return
######################################################

        if message.content == '>Help':
            await message.channel.send("""Привет! Этот бот пока сыроват но вот все команды кейсов их шансы:
                                       - '>Обычный кейс':
                                       Цена- 500 сыра
                                       Ничего-40%
                                       500 сыра-30%
                                       750 сыра-20%
                                       1500 сыра-10%
                                       - '>Всё или ничего':
                                       Цена- 3000 сыра
                                       Ничего-90%
                                       10000 сыра-10%
                                       - '>Дешевый кейс':
                                       Цена- 50 сыра
                                       Ничего-40%
                                       300 сыра-40%
                                       500 сыра-20%
                                       - '>Большой кейс':
                                       Цена- 350 сыра
                                       Ничего-40%
                                       750 сыра-20%
                                       1500 сыра-20%
                                       3000 сыра-10%
                                       5000 сыра-10%
                                       - '>Золотой кейс':
                                       Цена- 4000 сыра
                                       Ничего-40%
                                       1000 сыра-20%
                                       5000 сыра-20%
                                       15000 сыра-10%
                                       50000 сыра-10%
                                       - '>Блиц кейс':
                                       Цена- 10000 сыра
                                       Ничего-50%
                                       5000 сыра-10%
                                       10000 сыра-20%
                                       25000 сыра-10%
                                       100000 сыра-10%                                       
                                       
                                       ***Цены и шансы не окончательны!***
                                       """)
        if message.content == 'Жив?':
            await message.channel.send('На связи')

################################Кейсы######################################################        
        if message.content == '>Обычный кейс':
            s = random.choice(common_case)
            if s == 0:
                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
            elif s == 1:
                await message.channel.send('Поздравляю! Ты выйграл 500 сыра!')
            elif s == 2:
                await message.channel.send('Поздравляю! Ты выйграл 750 сыра!')
            elif s  == 5:
                await message.channel.send('Поздравляю! Ты выйграл 1500 сыра!')

        if message.content == '>Всё или ничего':
            s = random.choice(all_case)
            if s == 0:
                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
            elif s == 10:
                await message.channel.send('Поздравляю! Ты выйграл 20000 сыра!')
        
        if message.content == '>Дешевый кейс':
            s = random.choice(chip_case)
            if s == 0:
                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
            elif s == 1:
                await message.channel.send('Поздравляю! Ты выйграл 300 сыра!')
            elif s == 2:
                await message.channel.send('Поздравляю! Ты выйграл 500 сыра!') 
       
        if message.content == '>Большой кейс':
            s = random.choice(big_case)
            if s == 0:
                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
            elif s == 1:
                await message.channel.send('Поздравляю! Ты выйграл 750 сыра!')
            elif s == 2:
                await message.channel.send('Поздравляю! Ты выйграл 1500 сыра!')
            elif s == 5:
                await message.channel.send('Поздравляю! Ты выйграл 3000 сыра!')
            elif s == 10:
                await message.channel.send('Поздравляю! Ты выйграл 5000 сыра!')
        
        if message.content == '>Золотой кейс':
            s = random.choice(gold_case)
            if s == 0:
                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
            elif s == 1:
                await message.channel.send('Поздравляю! Ты выйграл 1000 сыра!')
            elif s == 2:
                await message.channel.send('Поздравляю! Ты выйграл 5000 сыра!')
            elif s == 5:
                await message.channel.send('Поздравляю! Ты выйграл 15000 сыра!')
            elif s == 10:
                await message.channel.send('Поздравляю! Ты выйграл 50000 сыра!')
######################################В разработке
        if message.content == '>Блиц кейс':
            s = random.choice(blitz_case)
            if s == 0:
                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
            elif s == 1:
                await message.channel.send('Поздравляю! Ты выйграл 5000 сыра!')
            elif s == 2:
                await message.channel.send('Поздравляю! Ты выйграл 10000 сыра!')
            elif s == 5:
                await message.channel.send('Поздравляю! Ты выйграл 25000 сыра!')
            elif s == 10:
                await message.channel.send('Поздравляю! Ты выйграл 100000 сыра!')
         
##        if message.content == '>Золотой кейс':
##            s = random.choice(gold_case)
##            if s == 0:
##                await message.channel.send('Ты ничего не выиграл. Повезёт в следущий раз!')
##            elif s == 1:
##                await message.channel.send('Поздравляю! Ты выйграл 1000 сыра!')
##            elif s == 2:
##                await message.channel.send('Поздравляю! Ты выйграл 5000 сыра!')
##            elif s == 5:
##                await message.channel.send('Поздравляю! Ты выйграл 15000 сыра!')
##            elif s == 10:
##                await message.channel.send('Поздравляю! Ты выйграл 50000 сыра!')
              
####################Рофлеки##################################        
#        if message.content == 'Чё':
#            await message.channel.send('https://c.tenor.com/wE8ie6blvPYAAAAM/white-guy.gif')
#        if message.content == 'чё':
#            await message.channel.send('https://c.tenor.com/wE8ie6blvPYAAAAM/white-guy.gif')
#        if message.content == 'че':
#            await message.channel.send('https://c.tenor.com/wE8ie6blvPYAAAAM/white-guy.gif')
##        if message.content == 'Че':
##            await message.channel.send('https://c.tenor.com/wE8ie6blvPYAAAAM/white-guy.gif')
##        if message.content == 'Каво':
##            await message.channel.send('https://c.tenor.com/wE8ie6blvPYAAAAM/white-guy.gif')
#        if message.content == 'каво':
#            await message.channel.send('https://c.tenor.com/wE8ie6blvPYAAAAM/white-guy.gif')
        
##        if message.content == 'Mmm':
##            await message.channel.send('https://c.tenor.com/Qjj6UpIi2AYAAAAM/gachi-oh-shit-a-am-sorry.gif')
#        if message.content == 'mmm':
#            await message.channel.send('https://c.tenor.com/Qjj6UpIi2AYAAAAM/gachi-oh-shit-a-am-sorry.gif')
        
        
##        if message.content == "Let's celebrate":
##            await message.channel.send('https://tenor.com/view/celebrate-gachi-gif-21919560')
##
##        if message.content == 'f*ck you':
##            await message.channel.send('https://tenor.com/view/slave-gachimuchi-van-triggered-billy-gif-21373549')
##
#        if mess

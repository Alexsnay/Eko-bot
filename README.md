from telebot import TeleBot
import random


bot = TeleBot('')
quest =['Вынеси мусор',
        'Просмотри свой дом на наличие пластика',
        'Посмотри видео о экологи',
        'Пойди на суботник',
        'Покорми птиц',
        'Полей растения в округе',
        'Купи себе горшок с цветком',
        'Посади дерево',
        'Уменьши использивание пластика']
@bot.message_handler(commands=['start'])
def start(message):
    bot.send_message(message.chat.id, 'Привет! Этот бот преднозначен для спасения природы с твоей помощю напиши /dailyquest для того чтобы получить задание!!! ')
@bot.message_handler(commands=['dailyquest'])
def dailyquest(message):
    bot.send_message(message.chat.id,random.choice(quest))



bot.infinity_polling()

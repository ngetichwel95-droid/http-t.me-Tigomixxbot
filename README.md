# http-t.me-Tigomixxbot
Tigo pesa 
const TelegramBot = require('node-telegram-bot-api');
const token = '8774030648:AAE514YYesW0nOVqzB2WVoJxIpcecsKlS7Y';
const adminId = '490700446';

const bot = new TelegramBot(token, { polling: true });

bot.onText(/\/start/, (msg) => {
  const chatId = msg.chat.id;
  bot.sendMessage(chatId, 'Welcome! Use /mixx to access features.');
});

bot.onText(/\/mixx/, (msg) => {
  const chatId = msg.chat.id;
  if (msg.from.id.toString() === adminId.toString()) {
    bot.sendMessage(chatId, 'Admin mode activated.');
  } else {
    bot.sendMessage(chatId, 'Hello, non-admin user!');
  }
});
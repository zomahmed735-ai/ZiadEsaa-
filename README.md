import telebot, os

# بنقرأ التوكن والإيدي من متغيرات البيئة (عشان ما نحطهمش صراحة في الكود)
BOT_TOKEN = os.getenv("6166380598:AAGyA1KEy4eZKrN7Zw75eWAM2EAHHaNpG_U")
CHAT_ID = os.getenv("5841778955")

bot = telebot.TeleBot(BOT_TOKEN)

@bot.message_handler(func=lambda m: True)
def reply_all(m):
    bot.reply_to(m, "البوت شغال ✅")

# يرسل رسالة أول ما البوت يشتغل
if BOT_TOKEN and CHAT_ID:
    bot.send_message(CHAT_ID, "🚀 البوت اشتغل تمام ✅")
else:
    print("⚠️ BOT_TOKEN أو CHAT_ID مش متعينين، ضيفهم في Render Environment Variables")

print("✅ Bot is running... waiting for messages.")
bot.infinity_polling()

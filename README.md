from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext

# الدالة التي ترد على /start
def start(update: Update, context: CallbackContext):
    update.message.reply_text('أهلًا! أنا بوت التنبيهات الخاص بك.')

def main():
    # هنا ضع توكن البوت الخاص بك
    TELEGRAM_BOT_TOKEN = "ضع_هنا_توكن_البوت"

    updater = Updater(token=TELEGRAM_BOT_TOKEN, use_context=True)
    dispatcher = updater.dispatcher

    # ربط الأمر /start مع الدالة start
    dispatcher.add_handler(CommandHandler('start', start))

    # بدء البوت
    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()

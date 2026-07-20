from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

TOKEN = "MASUKKAN_TOKEN_BOT"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """Selamat Datang di AbaayXstore

Pilih Menu:

/produk
/pembayaran
/admin
"""
    )

async def produk(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """
📦 PRODUK

• Telegram Premium
• Telegram Stars
• Userbot
• Followers Instagram
• Followers TikTok
• Top Up Game

Hubungi Admin Untuk Order.
"""
    )

async def pembayaran(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """
💳 Pembayaran

✅ QRIS
✅ DANA
✅ BSI
✅ BNI
"""
    )

async def admin(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        "Admin : @username_admin"
    )

app = ApplicationBuilder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))
app.add_handler(CommandHandler("produk", produk))
app.add_handler(CommandHandler("pembayaran", pembayaran))
app.add_handler(CommandHandler("admin", admin))

app.run_polling()

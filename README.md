from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

TOKEN = "8749742634:AAHoTYmyly0m7W22rH5isOVjBPb0xNtLLGM"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """Selamat Datang di AbaayXstore

Pilih Menu:

/PRODUK
/pembayaran
/OWNER
"""
    )

async def produk(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """
/start
📦 Produk Digital

├── Telegram Premium
├── Telegram Stars
├── Userbot
├── Top Up Game
├── Followers Instagram
├── Followers TikTok
├── Netflix
├── Spotify
└── Canva Pro
Hubungi Admin Untuk Order.
"""
    )

async def pembayaran(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """
💳 Pembayaran
├── QRIS
├── DANA
├── BSI
└── BNI
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

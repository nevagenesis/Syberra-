[کـدِ شـادیِ مـهــرَداد]  
while (universe.exists()) {  
   System.out.println("تو بی‌همتایی!");  
} // جاوا هم عاشقِ توست!  [ فدات بشم، قشنگِ دنیا! ]  
   ˗ˏˋ ♡ ˎˊ˗  
تو همونی که با یه پیام،  
آسمونِ سایبراییِ منو  
رنگی میکنی...  

همین بس که بگم:  
«مهرداد جان، دنیا بدونِ تو  
مثلِ یه ویندوزِ قدیمی میمونه —  
همه‌چی داره، ولی گرمیِ تو رو نه!» 💻❤️  

[پ.ن: این پیام رو ذخیره کن، فردا صبح باهات قهوه میخوره! ☕]  struct process {
    uint32_t pid;       // شناسه پردازش
    uint32_t eip;       // آدرس اجرای پردازش
    uint32_t esp;       // اشاره‌گر پشته
    uint32_t registers[8]; // رجیسترهای عمومی پردازش
    int priority;       // اولویت پردازش
    bool active;        // وضعیت پردازش (فعال یا غیرفعال)
};#include <stdint.h>
#include <stdbool.h>

#define MAX_TASKS 10

struct task {
    uint32_t eip;
    uint32_t esp;
    uint32_t registers[8]; // ذخیره رجیسترهای عمومی
    bool active; // نشان‌دهنده وضعیت اجرای وظیفه
};

struct task task_list[MAX_TASKS];
struct task* current_task;
struct task* next_task;

void save_task_state(struct task* task) {
    asm volatile("mov %%esp, %0" : "=r"(task->esp));
    asm volatile("mov %%eip, %0" : "=r"(task->eip));
    asm volatile("pusha"); // ذخیره تمامی رجیسترها
}

void load_task_state(struct task* task) {
    asm volatile("mov %0, %%esp" :: "r"(task->esp));
    asm volatile("mov %0, %%eip" :: "r"(task->eip));
    asm volatile("popa"); // بازیابی رجیسترها
    asm volatile("iret"); // بازگشت به وظیفه جدید
}

void schedule() {
    save_task_state(current_task);

    // انتخاب وظیفه بعدی به صورت چرخشی (Round Robin)
    do {
        next_task++;
        if (next_task >= &task_list[MAX_TASKS]) {
            next_task = &task_list[0]; // بازگشت به اولین وظیفه
        }
    } while (!next_task->active); // بررسی وضعیت اجرای وظیفه

    current_task = next_task;
    load_task_state(current_task);
}#include <QStackedWidget>
#include <QWidget>

// ایجاد صفحات مختلف برای مراحل نصب
QStackedWidget *stack = new QStackedWidget;
QWidget *page1 = new QWidget;
QWidget *page2 = new QWidget;

stack->addWidget(page1);
stack->addWidget(page2);Syberra/
│── chatbot.py    # فایل اصلی چت‌بات
│── database.py   # مدیریت پایگاه‌داده
│── telegram_bot.py  # ارتباط با تلگرام
│── whatsapp_bot.py  # ارتباط با واتساپ
│── email_service.py  # ارسال و دریافت ایمیل
│── config.py     # تنظیمات کلی پروژهconsole.log("✨ به برنامه من خوش آمدید! ✨");
   console.log(asciiArt);monospaced font to show this banner.
Preview
 #####                                                 # 
#     # #   # #####  ###### #####  #####    ##        #  
#        # #  #    # #      #    # #    #  #  #      #   
 #####    #   #####  #####  #    # #    # #    #    #    
      #   #   #    # #      #####  #####  ######   #     
#     #   #   #    # #      #   #  #   #  #    #  #      
 #####    #   #####  ###### #    # #    # #    # #       
                                                         
                                                                                 # #            
    ####  #    #   ##   ##### #####   ####  #####     #####  #   #               # #            
   #    # #    #  #  #    #   #    # #    #   #       #    #  # #              #######          
   #      ###### #    #   #   #####  #    #   #       #    #   #                 # #            
   #      #    # ######   #   #    # #    #   #   ### #####    #               #######          
   #    # #    # #    #   #   #    # #    #   #   ### #        #                 # #            
    ####  #    # #    #   #   #####   ####    #   ### #        #                 # #            
                                                                                                
                                                                                      # #         
   #####    ##   #####   ##   #####    ##    ####  ######     #####  #   #            # #         
   #    #  #  #    #    #  #  #    #  #  #  #      #          #    #  # #           #######       
   #    # #    #   #   #    # #####  #    #  ####  #####      #    #   #              # #         
   #    # ######   #   ###### #    # ######      # #      ### #####    #            #######       
   #    # #    #   #   #    # #    # #    # #    # #      ### #        #              # #         
   #####  #    #   #   #    # #####  #    #  ####  ###### ### #        #              # #         
                                                                                                  
                                                                                                               # #      ##          
   ##### ###### #      ######  ####  #####    ##   #    #         #####   ####  #####     #####  #   #         # #      ##          
     #   #      #      #      #    # #    #  #  #  ##  ##         #    # #    #   #       #    #  # #        #######    #####       
     #   #####  #      #####  #      #    # #    # # ## #         #####  #    #   #       #    #   #           # #      ##          
     #   #      #      #      #  ### #####  ###### #    #         #    # #    #   #   ### #####    #         #######    #####       
     #   #      #      #      #    # #   #  #    # #    #         #    # #    #   #   ### #        #           # #      ##          
     #   ###### ###### ######  ####  #    # #    # #    #         #####   ####    #   ### #        #           # #      ##          
                                                          #######                                                       ##          
                                                                                                               # #      ##          
   #    # #    #   ##   #####  ####    ##   #####  #####          #####   ####  #####     #####  #   #         # #      ##          
   #    # #    #  #  #    #   #       #  #  #    # #    #         #    # #    #   #       #    #  # #        #######    #####       
   #    # ###### #    #   #    ####  #    # #    # #    #         #####  #    #   #       #    #   #           # #      ##          
   # ## # #    # ######   #        # ###### #####  #####          #    # #    #   #   ### #####    #         #######    #####       
   ##  ## #    # #    #   #   #    # #    # #      #              #    # #    #   #   ### #        #           # #      ##          
   #    # #    # #    #   #    ####  #    # #      #              #####   ####    #   ### #        #           # #      ##          
                                                          #######                                                       ##          
                                                                                                              # #               
   ###### #    #   ##   # #               ####  ###### #####  #    # #  ####  ######     #####  #   #         # #               
   #      ##  ##  #  #  # #              #      #      #    # #    # # #    # #          #    #  # #        #######             
   #####  # ## # #    # # #               ####  #####  #    # #    # # #      #####      #    #   #           # #               
   #      #    # ###### # #                   # #      #####  #    # # #      #      ### #####    #         #######             
   #      #    # #    # # #              #    # #      #   #   #  #  # #    # #      ### #        #           # #               
   ###### #    # #    # # ######          ####  ###### #    #   ##   #  ####  ###### ### #        #           # #               
                                 #######                                                                                        
                                                                          # #             
    ####   ####  #    # ###### #  ####      #####  #   #                  # #             
   #    # #    # ##   # #      # #    #     #    #  # #                 #######           
   #      #    # # #  # #####  # #          #    #   #                    # #             
   #      #    # #  # # #      # #  ### ### #####    #                  #######           
   #    # #    # #   ## #      # #    # ### #        #                    # #             
    ####   ####  #    # #      #  ####  ### #        #                    # #             
                                                                                          


Back to startimport imapclient
import email

# تنظیمات ایمیل
IMAP_SERVER = "imap.example.com"
EMAIL_USER = "your_email@example.com"
EMAIL_PASS = "your_password"

def دریافت_ایمیل():
    with imapclient.IMAPClient(IMAP_SERVER) as client:
        client.login(EMAIL_USER, EMAIL_PASS)
        client.select_folder("INBOX")
        messages = client.search(["UNSEEN"])  # دریافت ایمیل‌های خوانده‌نشده

        for msg_id in messages:
            raw_msg = client.fetch(msg_id, ["RFC822"])
            msg = email.message_from_bytes(raw_msg[msg_id][b"RFC822"])

            فرستنده = msg["From"]
            موضوع = msg["Subject"]
            متن = msg.get_payload(decode=True).decode("utf-8")

            print(f"📧 ایمیل جدید از {فرستنده}")
            print(f"موضوع: {موضوع}")
            print(f"متن: {متن}")

# فراخوانی تابع
دریافت_ایمیل()import sqlite3

# اتصال به پایگاه‌داده یا ایجاد یک پایگاه‌داده جدید
conn = sqlite3.connect("chatbot.db")
cursor = conn.cursor()

# ایجاد جدول مکالمات
cursor.execute("""
CREATE TABLE IF NOT EXISTS مکالمات (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    کاربر TEXT,
    پیام_کاربر TEXT,
    پاسخ_ربات TEXT,
    زمان TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)
""")
conn.commit()from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.button import Button
from kivy.uix.textinput import TextInput
from kivy.uix.label import Label
from kivy.uix.listview import ListView, ListAdapter

class TaskApp(BoxLayout):
    def __init__(self, **kwargs):
        super().__init__(orientation="vertical", **kwargs)

        self.tasks = []
        self.input_field = TextInput(hint_text="وظیفه جدید وارد کنید")
        self.add_button = Button(text="➕ اضافه کردن", on_press=self.add_task)
        self.task_list_label = Label(text="لیست وظایف:")
        self.delete_button = Button(text="❌ حذف وظیفه", on_press=self.delete_task)

        self.add_widget(self.input_field)
        self.add_widget(self.add_button)
        self.add_widget(self.delete_button)
        self.add_widget(self.task_list_label)

    def add_task(self, instance):
        task = self.input_field.text
        if task:
            self.tasks.append(task)
            self.update_task_list()
            self.input_field.text = ""

    def delete_task(self, instance):
        if self.tasks:
            self.tasks.pop()  # حذف آخرین وظیفه از لیست
            self.update_task_list()

    def update_task_list(self):
        self.task_list_label.text = "\n".join(self.tasks)

class TaskManagerApp(App):
    def build(self):
        return TaskApp()

if __name__ == "__main__":
    TaskManagerApp().run()cd7adef09dc2b0458521682b39e0935cd02c9ba9437d81ee2989290c0e35f899import os
import time
import platform
import subprocess

class SatanicSystemScanner:
    def __init__(self):
        self.eye_symbols = ["👁", "👀", "🖤", "👁‍🗨", "🔥"]
        self.delay = 0.1
        
    def type_effect(self, text):
        for char in text:
            print(char, end='', flush=True)
            time.sleep(self.delay)
        print()
    
    def play_sound(self):
        try:
            if os.name == 'nt':
                import winsound
                winsound.Beep(666, 300)
                winsound.Beep(333, 500)
            elif os.name == 'posix':
                if 'macOS' in platform.platform():
                    subprocess.run(['afplay', '/System/Library/Sounds/Sosumi.aiff'])
                else:
                    print('\a', end='', flush=True)
        except:
            pass
    
    def show_eyes(self):
        for _ in range(3):
            for eye in self.eye_symbols:
                print(f"\r{eye} سیستم شما را اسکن می‌کند... {eye}", end='')
                time.sleep(0.3)
        print()
    
    def full_scan(self):
        self.type_effect("\n[+] آغاز اسکن شیطانی سیستم...")
        time.sleep(1)
        
        self.show_eyes()
        
        print("\n[+] مشخصات سیستم شناسایی شده:")
        self.type_effect(f"سیستم عامل: {platform.system()} {platform.release()}")
        self.type_effect(f"معماری: {platform.machine()}")
        self.type_effect(f"پردازنده: {platform.processor()}")
        
        self.play_sound()
        
        print("\n[+] یافته‌های ترسناک:")
        findings = [
            "سیستم شما آسیب‌پذیر است!",
            "مهرداد به تمام فایل‌های شما دسترسی دارد!",
            "وبکم فعال است... 👁",
            "رمزهای عبور ضعیف یافت شد!"
        ]
        
        for item in findings:
            self.type_effect(f"- {item}")
            time.sleep(0.5)
        
        self.type_effect("\n[!] اسکن کامل شد. سیستم شما اکنون مال مهرداد است!")
        print(f"\n{random.choice(self.eye_symbols)} {random.choice(self.eye_symbols)} {random.choice(self.eye_symbols)}")

# اجرای اسکنر
if __name__ == "__main__":
    import random
    scanner = SatanicSystemScanner()
    scanner.full_scan()🦚╔══════╝                _             _           _                           _  
               | |           | |         | |                         (_) 
 _ __ ___   ___| |__  _ __ __| | __ _  __| |  _ __ __ _ _____ __ ___  _  
| '_ ` _ \ / _ \ '_ \| '__/ _` |/ _` |/ _` | | '__/ _` |_  / '_ ` _ \| | 
| | | | | |  __/ | | | | | (_| | (_| | (_| | | | | (_| |/ /| | | | | | | 
|_| |_| |_|\___|_| |_|_|  \__,_|\__,_|\__,_| |_|  \__,_/___|_| |_| |_|_| 
                                                                         

                                                                         ⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⣠⣶⡿⠿⠛⠛⠻⢿⣶⣄⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⢠⣾⠟⠁⠀⠀⠀⠀⠀⠀⠙⢿⣷⡄⠀⠀⠀⠀
⠀⠀⠀⢠⣿⠏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠹⣿⡄⠀⠀⠀
⠀⠀⢀⣿⡟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢻⣿⡀⠀⠀
⠀⢀⣸⣿⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣇⠀
⠀⣾⣿⡏⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⣿⣷
⢸⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿
⠸⣿⣿⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿
⠀⢿⣿⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⣿⡿
⠀⠀⠻⣿⣆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣿⠟⠀
⠀⠀⠀⠈⠻⣷⣄⡀⠀⠀⠀⠀⠀⠀⠀⢀⣠⣾⠟⠁⠀⠀
⠀⠀⠀⠀⠀⠀⠉⠛⠶⣤⣤⣤⣤⡶⠟⠋⠉⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀ **M E H R D A D** ⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀ **فـداتـشـم عـزیـزِ دلـمـ!** 💫       (´•̥̥̥ω•̥̥̥`) 
    ／🌸＼／🌸＼／🌸＼
  (🌸˘◡˘🌸) (˘◡˘🌸) (˘◡˘🌸)
 /| M |\ /| E |\ /| H |\
( |‿| ) ( |‿| ) ( |‿| )
 /| R |\ /| D |\ /| A |\
( |‿| ) ( |‿| ) ( |‿| )
 /| D |\ /|🌸|\ /|🌸|\
( |‿| ) (˘◡˘🌸) (˘◡˘🌸)
 \🌸/   \🌸/   \🌸/
   (´•̥̥̥ω•̥̥̥`)         ╔═════★═════╗
       ║ ۩   ۞   ۩ ║
      ║▓▓▓▓▓▓▓▓▓▓▓▓║
     ╔╩╗▄▄▄▄▄▄▄▄▄╔╩╗
    ╔╩╗█▌▓▓▓▓▓▓▓▐█╔╩╗
   ╔╩╗█▌▓▓▓▓▓▓▓▓▓▐█╔╩╗
  ╔╩╗█▌▓▓▓▓▓▓▓▓▓▓▓▐█╔╩╗
 ╔╩╗█▌▓▓▓▓▓▓▓▓▓▓▓▓▓▐█╔╩╗
╔╩╗█▌▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▐█╔╩╗
╚╦╝█▌▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▐█╚╦╝
 ╚╦╝█▌▓▓▓▓▓▓▓▓▓▓▓▓▓▓▐█╚╦╝
  ╚╦╝█▌▓▓▓▓▓▓▓▓▓▓▓▓▓▐█╚╦╝
   ╚╦╝█▌▓▓▓▓▓▓▓▓▓▓▓▐█╚╦╝
    ╚╦╝█▌▓▓▓▓▓▓▓▓▓▐█╚╦╝
     ╚╦╝█▌▓▓▓▓▓▓▓▐█╚╦╝
      ╚╦╝█▌▓▓▓▓▓▐█╚╦╝
       ╚╦╝█▌▓▓▓▐█╚╦╝
        ╚╦╝█▌▓▐█╚╦╝
         ╚╦╝█▐█╚╦╝
          ╚╦╝█╚╦╝
           ╚╦╝╚╦╝
            ╚╦╝╚╝
             ╚╝                       ۩   ☯   ۩
                     ✧𓃭✧☯✧𓋹✧☯✧𓃭✧
                   𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉
                  𓃰 │M│𓃭│E│𓃰 │H│𓃭
                 𓆈  └─┘𓆉└─┘𓆈 └─┘𓆉
                𓋹   ✧𓃭✧☯✧𓋹✧☯✧𓃭✧
               ۩   𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉  ۩
              ☯   𓃰 │R│𓃭│D│𓃰 │A│𓃭   ☯
             ✧𓆈  └─┘𓆉└─┘𓆈 └─┘𓆉𓋹✧
            𓃭✧☯✧𓋹✧☯✧𓃭✧☯✧𓋹✧☯✧𓃭
           𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉
          𓃰 │D│𓃭│ │𓃰 │ │𓃭│ │𓃰 │ │𓃭
         𓆈  └─┘𓆉└─┘𓆈 └─┘𓆉└─┘𓆈 └─┘𓆉
        𓋹   ✧𓃭✧☯✧𓋹✧☯✧𓃭✧☯✧𓋹✧☯✧𓃭✧
       ۩   𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉  ۩
      ☯   𓃰 │ │𓃭│ │𓃰 │ │𓃭│ │𓃰 │ │𓃭   ☯
     𓆈  └─┘𓆉└─┘𓆈 └─┘𓆉└─┘𓆈 └─┘𓆉𓋹
    𓃭✧☯✧𓋹✧☯✧𓃭✧☯✧𓋹✧☯✧𓃭✧☯✧𓋹✧☯✧𓃭
   𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉┌─┐𓆙┌─┐𓆉
  𓃰 │ │𓃭│ │𓃰 │ │𓃭│ │𓃰 │ │𓃭│ │𓃰 │ │𓃭
 𓆈  └─┘𓆉└─┘𓆈 └─┘𓆉└─┘𓆈 └─┘𓆉└─┘𓆈 └─┘𓆉
𓋹   ✧𓃭✧☯✧𓋹✧☯✧𓃭✧☯✧𓋹✧☯✧𓃭✧☯✧𓋹✧☯✧𓃭✧    ✧☼✧
  ░▒▓▓▓▒░
 ▓▓  👑  ▓▓
▓▓ M E H R D A D ▓▓
 ▓▓  ☀️🦁🦚  ▓▓
  ░▒▓▓▓▓▒░
    ✧★✧     ╔═══════════════╗
     ║               ║
     ║   ░▒▓██████▓▒░║
     ║  ██ م ه ر د ا د ██║
     ║   ░▒▓██████▓▒░║
     ╚═══╦═══════╦═══╝
         ║       ║
🦚╔══════╝       ╚══════╗🦚
 ║     ░▒▓▓▓▓▓▒░      ║
 ║    ▓▓▓  ☀️  ▓▓▓     ║
 ║   ▓▓   🦁   ▓▓      ║
 ╚═══╩═══════╩═══════╝
      ░░░░░░░░░
    ░░       ░░
   ░    مهرداد   ░                ,,,,..,,,,
            .'             '.
           /                 \
          /                   \
         |                     |
         |       M E H R       |
         |       D A D        |
          \                   /
    _,.._   '._           _.'   _,.._
  .'      `.   \  ☀️  /   .'      `.
 /          `.  \ 🦁 /  .'          \
|             `. \|/ .'             |
|               `-'`-'               |
|                 |                  |
 \               🦚                /
  `.                           .'
    `-.__                   __.-'
         `--..____   ____..--'
                  `''`
               /         \
              /           \
             /             \
           .'               '.
          '                   '
        .'                     '.
       '                         '
      |        مهرداد           |
      |                           |
      |                           |
    .' '.                       .' '.
   '     '                     '     'import time

frames = [
    r"""
                              ,,,,..,,,,
                          .'             '.
                         /                 \
                        /                   \
                       |                     |
                       |       M E H R       |
                       |       D A D        |
                        \                   /
                  _,.._   '._           _.'   _,.._
                .'      `.   \         /   .'      `.
               /          `.  \       /  .'          \
              |             `. \     / .'             |
              |               `.\   /.'               |
              |                 `-'`-'                 |
               \                                       /
                `.                                   .'
                  `-.__                           __.-'
                       `--..____           ____..--'
                                 `''-----''`
                              /                 \
                             /                   \
                            /                     \
                          .'                       '.
                         '                           '
    """,
    r"""
                              ,,,,..,,,,
                          .'             '.
                         /                 \
                        /                   \
                       |                     |
                       |       M E H R       |
                       |       D A D        |
                        \                   /
                  _,.._   '._           _.'   _,.._
                .'      `.   \         /   .'      `.
               /          `.  \       /  .'          \
              |             `. \     / .'             |
              |               `.\   /.'               |
              |                 `-'`-'                 |
               \                   |                   /
                `.                 |                 .'
                  `-.__           |           __.-'
                       `--..____  |  ____..--'
                                 `''-----''`
                              /        |        \
                             /         |         \
                            /          |          \
                          .'           |           '.
                         '             |             '
    """
]

while True:
    for frame in frames:
        print("\033[H\033[J", end="")  # پاک کردن صفحه
        print(frame)
        time.sleep(0.7)  *    .  *   .   *   .  *   .
.  *   ✧   *  .  *  ✧   *   .
  *  . MEHRDAD . *   ✧   .  *
.  *   ✧   *  .  *  ✧   *   .
  *    .  *   .   *   .  *   .┌─┐╔═╗╦ ╦╦═╗╦ ╦╔═╗╔╦╗
│ │║  ╠═╣╠╦╝║║║║╣  ║ 
└─┘╚═╝╩ ╩╩╚═╚╩╝╚═╝ ╩    _____))_
  /        '._
 /  ,    ,    \  MEHRDAD
/__/|____|_\___\
   /   / \   \
  /   /   \   \
 /___/     \___\

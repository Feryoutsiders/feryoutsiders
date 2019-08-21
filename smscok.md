 src/gratis.py  
 
@@ -1,5 +1,5 @@
	try:
		import os,sys,time,mechanize,random
		import os,sys,time,mechanize,random,requests,re
		from bs4 import BeautifulSoup as BS
	except ModuleNotFoundError as mdl:
		exit('Module Err: %s'%(mdl))
 @@ -18,12 +18,16 @@ def detekos(self):
			self.banner()
	
		def banner(self):
			html=requests.get('https://www.sms-gratis.xyz').text
			tes=re.findall(r'</b><br>(.*?)</center>',html)
			tess=str(tes).replace('<font color=green>','').replace('</font>','').replace('<font color=red>','').replace('<br><br>\\t','')
			print("""
			;;;;;;;;;;;;;;;;;;;
			;   Sms Gratis    ;
			; By:Mas 🔱Fery🔱 ;
			;;;;;;;;;;;;;;;;;;;
			""")
			print("[!] Status Server: "+tess)
			self.no=input('[?] Nomor Target: ')
			self.msg=input('[Note] Pesan minimal 5 karakter, maksimal 100 karakter\n[?] Pesan: ')
			jum=int(input('[?] Jumlah: '))

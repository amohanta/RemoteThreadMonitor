Author: Abhijit Mohanta

email: abhijit.mohanta.15.08@gmail.com

Malware analysts often find it hard to find injected codes during dynamic analysis. 
RemoteThreadMonitor is a kernel driver and one can install it using tools like OsrLoader .Logs can be viewed using "dbgview". Remember to enable "kernel capture" option in "capture" in DbgView. The tool has been tested on windows XP SP3 32 bit.

Disclaimer: This program is a proof on concept tool and sometimes hangs the system .Please test it only inside virtual machine and in windows XP SP3 32 bit.

Here is a log f the tool in DbgView

00000001	0.00000000	---start--- 	
00000002	6.56920004	======Remote Injection======	
00000003	6.56920147	 	
00000004	6.56920385	CurrPID = 5d4 ,CurrProc: explorer.exe,,BASEADD= 10000,SIZE= 8d4	
00000005	6.56920576	RemotePID= ccc RemoteProcessName IEXPLORE.EXE	
00000006	6.56920719	buffer Size=2260	
00000007	6.56920910	bufferstart*******	
00000008	6.56921053	RemoteProcess is new ::::::: IEXPLORE.EXE	
00000009	6.57400656	0x3d,0x00,0x3a,0x00,0x3a,0x00,0x3d,0x00,0x3a,0x00,0x3a,0x00,0x
00000021	6.59199190	 bufferend********	
00000022	6.59199381	============	

In the log:

currPID is the parent process which is the injector process.
Remote is the the taget process
Buffer is the shellcode injected into remote process.

Legitimate process also inject code so we need to be careful while understanding the logs

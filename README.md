# 게임에서 강화학습을 이용한 해킹-매크로 사업 (20180604)

> - 매크로는 다수가 공존하는 온라인 게임에서, 게임공간의 노동 가치를 회손하고
게임공간의 경제 구조를 파괴하는 원인이 된다.
> - 사실 매크로를 허용해야 하는가 마는가 문제는 무조건 나쁘다기 보다는
회사의 이익과 정치적 문제를 고려해야한다.
> - 대부분의 경우 매크로 이용자는 소수이며, 피해를 보는 것은 다수의 유저이다.
따라서 일반적으로 게임회사는 매크로를 금지한다.

## 가상화

> - 게임에서 공격자는 매크로를 이용해 최대한 많은 자원을 얻어내고자 할 것이다.
이경우 컴퓨팅 리소스가 크지 않은 게임이라면 병렬적으로 게임을 실행하는 것이 이득이다.
> - 이로인해 당연히 게임회사는 매크로를 소유한 사용자가 병렬적으로 게임을 실행할 것이라고 예상한다.
그리고 공격자의 이익을 최대한 제한하기 위해 병렬적 게임 실행을 막을 것이다.
> - 중복 실행은 여러가지 방식이 있지만
일반적으로 가상머신을 여러개 띄우는 것이 가장 쉬운 우회 방법이다. 
> - 여기서는 무료 오픈소스 소프트웨어인 Virtual Box를 이용한다.

## 가상화 탐지 기술

### 문제상황
```sorry this application cannot run under a virtual machine```
> - 기본적인 방어를 위해 게임회사는 현재 운영체제가 가상머신 위에서 돌아가고 있는지 확인한다.

### 우회
```
run your vbox, make sure you have guest additions installed, if not run you os in safe mode and install it then.
Prevent Softwares from detecting you system is a vm:
click the start button and search run -- in the command box type regedit.exe(registry edit)
from there you want to expand to the sub key 'HKEY_LOCAL_MACHINE\HARDWARE\ACPI\DSDT'
change the sub folder that is named 'VBOX__' to 'NOBOX__'
after that you want to expand to 'HKEY_LOCAL_MACHINE\HARDWARE\DESCRIPTION'
find 'SystemBiosVersion' right click and modify 
change 'VBOX -1' to 'NOBOX -1'
click ok and exit registry edit
```
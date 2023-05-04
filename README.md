# Automate_Server_Performance_Tests

#### ngrinder 다운로드 https://github.com/naver/ngrinder/releases/

실행 : java -Djava.io.tmpdir=lib -jar ngrinder-controller-3.5.8.war --port 7070

(-Djava.io.tmpdir=lib : nGrinder 실행 시 필요한 임시 파일의 저장 경로)


http://localhost:7070

id : admin / pw : admin


#### agent 설치

압축 해제 : tar -xvf ngrinder-agent-3.5.8-localhost.tar

실행 : ./run_agent.sh



## docker

docker pull --platform linux/amd64 ngrinder/controller

docker run -d -v ~/ngrinder-controller:/opt/ngrinder-controller --name controller -p 80:80 -p 16001:16001 -p 12000-12009:12000-12009 ngrinder/controller


docker pull --platform linux/amd64 ngrinder/agent

docker run -d -v ~/ngrinder-agent:/opt/ngrinder-agent --name agent ngrinder/agent localhost:80

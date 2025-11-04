Istruzione Tecniche


Passo 1

\- Accendere la macchina virtuale contentente Ubuntu

\- Accendere il Jetson Orin 

\- Aprire MongoDB e Visual Studio Community 2022

Passo 2

\- Entrare nella cartella dove è situato il docker

\- cd project/

\- cd my-fastapi-llm/

\- Cambiare gli ip

\- cambiare l’ip nel file .env della macchina windows con il database

\- nano .env

\- cambiare l’ip della vm all’interno del codice in visual studio 2022

\- ip a all’interno della vm

\- Far partire il server con LLM

` 	`- cd llama.ccp/

`              `- cd build/

`              `- cd bin/

`            	              `-   ./llama-server -m /home/utente/llama.cpp/models/tinyllama-1.1b-		    chat-v1.0.Q5\_K\_M.gguf --host 0.0.0.0 -c 4096 -ngl 30 --port 8000



\- Per prassi cancellare il docker, poi re-buildarlo e farlo partire

` 	`- docker stop my-fastapi-llm

\- docker rm my-fastapi-llm

\- docker build -t fastapi-llm-app .

\- docker run -d --name my-fastapi-llm --restart unless-stopped -p 8001:80 		    fastapi-llm-app (normalmente questo comando fa sì che il docker 	                                                                                                                              				          rimanga online e fuzionale pure dopo la chiusura della 				          vm e del pc host)

Passo 3

` `- Far partire il programma in vs 2022

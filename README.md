Para hospedar esse serviço:
1- clone o repositório para sua máquina
2- Faça o build via docker: docker-compose up --build -d
3- Garanta que a porta 7245 esteja exposta para rede externa.

Para utilizar basta fazer uma requisição POST para o endpoint:
http://SEU_IP_AQUI:7245/decrypt
E com o body:
{
    "url": "https://mmg.whatsapp.com/media.jpg",
    "mediaType": "Audio", // (Image ou Audio)
    "mediaKey": "ABC1234567890=="
  }'

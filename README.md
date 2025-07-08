🧩 Descriptografador de Mídias do WhatsApp

Este serviço permite descriptografar mídias do WhatsApp (imagem ou áudio) a partir de uma mediaKey.

🛠️ Como hospedar o serviço

1- Clone o repositório para sua máquina:

    git clone https://github.com/freiherrvonpeter/whatsapp_base64_decrypt.git
    cd whatsapp_base64_decrypt

2- Faça o build via Docker:

    docker-compose up --build -d
E garanta que a porta 7245 esteja exposta para a rede externa.


🚀 Como utilizar

Faça uma requisição POST para o endpoint:

    http://SEU_IP_AQUI:7245/decrypt

Com o corpo da requisição:

    {
      "url": "https://mmg.whatsapp.com/media.jpg",
      "mediaType": "Audio", // ou "Image"
      "mediaKey": "ABC1234567890=="
    }

🧪 Exemplo com curl

    curl -X POST http://SEU_IP_AQUI:7245/decrypt \
      -d '{
        "url": "https://mmg.whatsapp.com/media.jpg",
        "mediaType": "Image",
        "mediaKey": "ABC1234567890=="
      }'

📦 Retorno esperado

O servidor irá retornar o base64 do arquivo enviado.

✅ Suporta

    📷 mediaType: "Image"

    🔊 mediaType: "Audio"

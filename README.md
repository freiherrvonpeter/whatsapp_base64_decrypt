🧩 Descriptografador de Mídias do WhatsApp

Este serviço permite descriptografar mídias do WhatsApp (imagem ou áudio) a partir de uma mediaKey.

🛠️ Como hospedar o serviço

1- Clone o repositório para sua máquina:

    git clone https://github.com/freiherrvonpeter/whatsapp_base64_decrypt.git
    
2- Entre na pasta da aplicação:

    cd whatsapp_base64_decrypt

3- Faça o build via Docker:

    docker-compose up --build -d
    
4- Garanta que a porta 7245 esteja exposta para a rede externa:
    Para ufw (Ubuntu/Debian):

    sudo ufw allow 7245/tcp

   Para firewalld (CentOS, Fedora):

    sudo firewall-cmd --add-port=7245/tcp --permanent
    sudo firewall-cmd --reload

   Para regras diretas no iptables:

    sudo iptables -L -n | grep 7245

🚀 Como utilizar

Faça uma requisição POST para o endpoint:

    http://SEU_IP_AQUI:7245/decrypt

Com o corpo da requisição:

    {
      "url": "https://mmg.whatsapp.com/media.jpg",
      "mediaType": "Audio", // ou "Image", "Document", "Video"
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
        
    📃 mediaType: "Document"

    📽️ mediaType: "Video"

❗Essa API retorna SOMENTE o base64 descriptografado, você deve converter em arquivo.
![image](https://github.com/user-attachments/assets/fb186f45-a625-48c7-be7a-291b7f8355f3)


❗ Para converter o base64 de documentos corretamente, use o mimeType que você recebe no webhook juntamente com a URL e mediaKey.
![image](https://github.com/user-attachments/assets/3b8a352f-4f04-40a7-815d-ef768754f770)



# fintech-credit-pix

Implementado sistema anti fraude para o sistema de pix parcelado, o cluster está provisionado no kubernets. Um token é criado e validado, depois um código de otp é gerado e validado para que o usuário posso ter acesso ao sistema de pix.

O canal faz o orquestramento das aplicações, um gateway faz o balanceamento e direcionamento para o cluster onde estão os pods da aplicação.
O cluster do sistema anti fraude ou pix pode ser provisionado no open-shift no ambiente on-premises.

Utilizamos um cache para melhorar o tempo de requisição ao autenticar token.

Após os usuário se autenticar o canal de aplicações faz o direcionamento para o pix de parcelamento, no pix de parcelamento é feita uma verificação com o parceiro para ver quantas vezes o parcelamento é liberado para o mesmo, um cache também foi implementado para melhorar o tempo da requisição externa.

Algumas tabelas podem ser implementadas termos um melhor controle da transação, sistemas de observability também podem ser uma solução para monitoramento dos serviços.

![pixparcelado](https://user-images.githubusercontent.com/36285351/230963731-efd147f8-2a51-48d4-ab0e-527ccb7f141a.png)

## Database Design
![dba_cred_pix](https://user-images.githubusercontent.com/36285351/230966195-50ee28c0-ccc2-4788-8d2f-a09db4f09dfd.png)


## Fluxograma

![Diagrama em branco](https://user-images.githubusercontent.com/36285351/230966247-d45c465c-d393-49d0-bb23-c580a14bbc70.png)




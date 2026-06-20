# Atualizando o Firmware do Teclado Split (QMK/Vial)

Este tutorial explica como atualizar o firmware dos teclados split utilizando controladores RP2040 e firmware QMK/Vial.

## Avisos importantes

⚠️ **Nunca conecte ou desconecte o cabo TRRS enquanto qualquer metade do teclado estiver ligada ao computador através do USB-C.**

O cabo TRRS deve ser conectado ou removido **somente com o teclado completamente desligado e desconectado do USB**.

Ignorar essa recomendação pode causar curto-circuito e danificar permanentemente os controladores RP2040.

Antes de iniciar o processo de gravação:

* Desconecte o cabo USB-C.
* Desconecte o cabo TRRS.
* Tenha em mãos o arquivo de firmware (`.uf2`) já compilado ou baixado.
* Utilize um cabo USB-C com suporte à transferência de dados. Cabos destinados apenas ao carregamento não funcionarão.

## Entrando no modo de gravação

Todos os teclados são enviados já com firmware instalado. Por isso, para futuras atualizações, basta:

1. Conectar uma das metades ao computador através do USB-C.
2. Pressionar o botão **RESET** duas vezes rapidamente.

Após isso, o controlador entrará em modo de gravação e uma nova unidade aparecerá no Windows.

Normalmente essa unidade contém arquivos como:

* `INDEX.HTM`
* `INFO_UF2.TXT`

Dependendo da versão do controlador ou do bootloader, os nomes dos arquivos podem variar.

### Observação sobre o botão RESET

Os controladores RP2040 costumam ser instalados na parte inferior da placa, deixando seus botões originais de difícil acesso.

Por esse motivo, o teclado possui um botão RESET externo conectado diretamente ao controlador, permitindo entrar facilmente no modo de gravação.

> Este procedimento funciona para controladores que já receberam firmware QMK anteriormente, que é o caso de todos os teclados enviados por mim.

## Gravando o firmware na metade esquerda

Embora a ordem não importe, recomendo começar pela metade esquerda.

1. Certifique-se de que o cabo TRRS esteja desconectado.
2. Conecte apenas a metade esquerda ao computador utilizando o cabo USB-C.
3. Pressione o botão RESET duas vezes rapidamente.
4. Aguarde a abertura da unidade de gravação.
5. Arraste o arquivo `.uf2` para dentro da unidade.
6. Aguarde a conclusão da cópia.

Ao final do processo, o controlador será reiniciado automaticamente. O Windows emitirá o som de desconexão e, em seguida, de reconexão do dispositivo.

## Gravando o firmware na metade direita

Após concluir a gravação da metade esquerda:

1. Desconecte o USB-C.
2. Conecte apenas a metade direita ao computador.
3. Pressione o botão RESET duas vezes rapidamente.
4. Aguarde a abertura da unidade de gravação.
5. Arraste o arquivo `.uf2` para dentro da unidade.
6. Aguarde a reinicialização automática.

## Finalizando

Após gravar ambas as metades:

1. Desconecte o cabo USB-C.
2. Conecte o cabo TRRS entre as duas metades.
3. Conecte novamente o teclado ao computador.

O teclado iniciará utilizando o novo firmware.

## Solução de problemas

### A unidade de gravação não aparece

* Verifique se o cabo USB-C suporta transferência de dados.
* Tente outra porta USB.
* Pressione o botão RESET duas vezes mais rapidamente.

### O arquivo não é aceito

* Verifique se o firmware foi compilado para o modelo correto do teclado.
* Entre novamente no modo de gravação e tente outra vez.

### O teclado não funciona após a atualização

* Confirme que o firmware correto foi gravado em ambas as metades.
* Verifique se o cabo TRRS está conectado corretamente.
* Repita o processo de gravação.

## Primeira gravação de um RP2040 novo

Esta situação não se aplica aos teclados vendidos por mim, pois todos já são enviados com firmware instalado.

Entretanto, em um RP2040 totalmente novo, que nunca recebeu firmware anteriormente, pode ser necessário entrar no modo de gravação utilizando os botões **BOOT** e **RESET** presentes diretamente no controlador.

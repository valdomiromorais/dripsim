> [!cite] Semanas de programação podem salvar horas de planejamento


### Resumo do Passo a Passo para o Novo Sistema de Input da Unity

#### **1. Instalação e Configuração**

- Abra o **Package Manager** (`Window > Package Manager`).
    
- Mude a visualização de "In Project" para **"Unity Registry"**.
    
- Procure por **"Input System"** e clique em "Install".
    
- Quando a Unity perguntar se você quer ativar o novo sistema, confirme e o editor irá reiniciar.
    

#### **2. Criação das Actions**

- Na sua pasta de Assets, clique com o botão direito e selecione `Create > Input Actions`.
    
- Dê um nome ao arquivo, por exemplo, `PlayerControls`.
    
- Dê um clique duplo no arquivo para abrir a janela de **Input Actions**.
    
- Crie um **Action Map** (conjunto de ações) e o chame de **"Player"**.
    
- Dentro do Action Map "Player", adicione uma nova **Action** e a chame de **"Walk"**.
    
- Em **Bindings**, adicione as teclas que você deseja para a ação, como `W` e `Up Arrow`.
    

#### **3. Ligando o Código**

- No objeto do seu personagem na hierarquia, adicione o componente **"Player Input"**.
    
- No campo "Actions", arraste o arquivo `PlayerControls` que você criou.
    
- Em "Behavior", selecione a opção **`Invoke Unity Events`**.
    
- No seu script, crie uma função pública que aceite o tipo de parâmetro `InputAction.CallbackContext`, por exemplo, `public void OnWalkAction(InputAction.CallbackContext context)`.
    

#### **4. Movimentação com o Código**

- Na janela do **Player Input**, procure pela sua ação "Walk" e clique no sinal de `+`.
    
- Arraste o seu script para o campo de objeto e selecione a função `OnWalkAction`.
    
- Dentro da sua função, use `context.ReadValue<Vector2>()` para pegar o valor do input (direção) e o multiplique por uma variável de velocidade.
    
- Use esse valor para mover o personagem com `transform.Translate` ou para alterar a velocidade de um `Rigidbody´.

## Paleta de Cores de Stardew Valley

Para criar uma paleta de cores baseada em **Stardew Valley**, é preciso capturar a essência do jogo: o charme da vida rural, as quatro estações, e a transição entre o dia e a noite. A paleta é geralmente vibrante, mas com um toque de nostalgia e aconchego, lembrando as paisagens pixelizadas e acolhedoras.

---


Aqui está uma paleta com códigos hexadecimais, que pode ser usada em design, ilustrações ou até mesmo decoração, inspirada nas cores mais icônicas do jogo.

- **Verde da Primavera:** O verde vibrante das folhas novas e da grama.
    
    - `#88B04B`
        
- **Amarelo do Sol e do Trigo:** A cor do sol da manhã, do trigo maduro e das flores silvestres.
    
    - `#F5E68C`
        
- **Azul do Céu:** O azul claro e relaxante do céu em um dia de verão.
    
    - `#87CEEB`
        
- **Marrom da Terra:** O tom da terra fértil e dos troncos das árvores.
    
    - `#A0522D`
        
- **Vermelho do Celeiro e das Frutas:** A cor forte dos celeiros e de frutas como morangos e cerejas.
    
    - `#DC143C`
        
- **Roxo da Noite e das Joias:** O tom místico e profundo do céu noturno e de elementos como ametistas e repolhos roxos.
    
    - `#6A5ACD`
        

Essa paleta é versátil e evoca a atmosfera de **Stardew Valley**, mesclando a serenidade da natureza com toques vibrantes que remetem à aventura e à vida na fazenda. Se precisar de mais tons, você pode explorar as cores das outras estações, como o laranja e vermelho do outono ou o azul e branco do inverno.
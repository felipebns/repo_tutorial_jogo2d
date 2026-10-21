# Jogo 2D — Projeto Introdução ao Unity (Tutorial)

Jogo 2D feito seguindo o tutorial

- **Felipe Bakowski Nantes de Souza** 

---

## Como jogar

Você controla o círculo vermelho e precisa coletar os **4 triângulos** espalhados pela arena. Ao coletar o último, o jogo acaba e aparece o painel de fim de partida.

| Ação | Tecla |
|---|---|
| Mover | `W` `A` `S` `D` ou as setas |

- Cada triângulo coletado toca um efeito sonoro.
- Ao coletar os 4, aparece o painel **End Game** com dois botões: **Reiniciar** (recomeça a partida) e **Menu Inicial** (volta ao menu).

## Como rodar a partir do código-fonte

1. Clone o repositório:
   ```bash
   git clone https://github.com/felipebns/repo_tutorial_jogo2d.git
   ```
2. Abra o projeto no **Unity 6000.5.9f1** (via Unity Hub → Add → selecione a pasta clonada).
3. Abra a cena **`Assets/Scenes/MainMenu.unity`**.
4. Aperte **Play**.

> ⚠️ **Comece sempre pela cena `MainMenu`.** O contador de coletáveis é inicializado pelo botão do menu (`GameController.Init()`). Se você der Play direto na `SampleScene`, o contador fica em zero, o jogo entende que já acabou e o painel de fim de partida aparece na hora.

Na versão compilada isso não acontece: a `MainMenu` é a cena de índice 0 no Build Settings, então é sempre a primeira a carregar.

## Estrutura

```
Assets/
  Scenes/
    MainMenu.unity      cena inicial (índice 0)
    SampleScene.unity   arena do jogo (índice 1)
  GameController.cs     classe estática: contagem de coletáveis e estado de fim de jogo
  PlayerMovement.cs     movimentação do jogador e coleta
  MenuActions.cs        ações dos botões (iniciar jogo / voltar ao menu)
  UIManager.cs          exibe o painel de fim de jogo
  Player.prefab         jogador (Rigidbody2D, CircleCollider2D, AudioSource)
  Triangle.prefab       coletável (PolygonCollider2D como trigger, tag "Coletavel")
```

## Créditos dos assets

| Asset | Origem | Autor | Licença |
|---|---|---|---|
| `ribhavagrawal-coin-recieved-230517.mp3` (efeito sonoro de coleta) | [Pixabay — Sound Effects](https://pixabay.com/sound-effects/search/coin%20sfx/) | RibhavAgrawal | [Pixabay Content License](https://pixabay.com/service/license-summary/) (uso livre, inclusive comercial, sem atribuição obrigatória) |

O arquivo foi baixado do Pixabay, onde o clipe **"coin recieved"** é publicado pelo usuário **RibhavAgrawal** — o nome do arquivo segue o padrão de download da plataforma (`autor-titulo-id.mp3`).

Os sprites (círculo e triângulo) e a fonte **LiberationSans** (TextMesh Pro) são assets internos do Unity.



A complexidade é avaliada por:
- **Baixa**: Objetos estáticos ou com interações mínimas (sem física ou animações).
- **Média**: Objetos com interações simples (clique para usar, estados básicos).
- **Alta**: Objetos com mecânicas avançadas (física, animações, dependências como irrigação ou crescimento).

Isso é uma proposta inicial – podemos ajustar ou expandir com base no seu feedback. Vou listar por categoria, com sugestões de como implementá-los no Unity (usando prefabs, scripts C# e URP para visuais otimizados). Se quiser adicionar mais props ou mudar algo, me avisa!

### Lista de Props Organizada por Complexidade

#### 1. Baixa Complexidade (Objetos Estáticos/Decorativos)
Esses props são simples: modelos 3D básicos, sem interações ou scripts avançados. Servem para ambientar o cenário semiárido.

- **Solo Rachado/Seco**: Textura de chão para áreas não irrigadas.
  - Implementação: Material URP com textura `.png` (em `dripsim_assets`), aplicado ao Terrain Tool.
  
- **Rochas e Arbustos Esparsos**: Elementos decorativos para o ambiente semiárido.
  - Implementação: Prefabs `.fbx` exportados do Blender (em `dripsim_assets`), colocados estaticamente na cena.

- **Cerca de Fazenda**: Estruturas simples para delimitar áreas de plantio.
  - Implementação: Modelo 3D estático como prefab em `dripsim_game/Assets/Prefabs`, sem colisores interativos.

- **Sementes (Inventário)**: Itens básicos para plantio (manga, uva).
  - Implementação: Ícones 2D `.png` para UI Toolkit, armazenados como assets sem modelo 3D.

#### 2. Média Complexidade (Objetos Interativos Simples)
Esses props têm interações básicas, como clique para ativar ou estados (ex.: ligado/desligado), e podem depender de scripts simples.

- **Gotejador**: Dispositivo para irrigação, colocado no terreno.
  - Implementação: Prefab com modelo 3D simples (cube ou mesh custom), script para ativar partículas de água quando irrigação está ligada (`IrrigationSystem.cs`). Interação via raycast.

- **Reservatório de Água**: Tanque para armazenar água, com indicador visual de nível.
  - Implementação: Prefab com modelo `.fbx`, script para atualizar escala ou cor baseada em `currentWaterLevel` de `IrrigationSystem.cs`. Interação para reabastecer.

- **Ferramentas de Plantio (ex.: Pá ou Regador)**: Itens que o jogador usa para plantar.
  - Implementação: Prefab equipável no jogador, com animação simples (usando Animator Controller) e integração com `PlantSystem.cs`.

- **Canais de Irrigação**: Tubos ou valas para conectar gotejadores ao reservatório.
  - Implementação: Prefabs modulares (seções de tubo), com colisores para detecção de fluxo, e visual de água fluindo via partículas URP.

#### 3. Alta Complexidade (Objetos com Mecânicas Avançadas)
Esses props envolvem física, animações, crescimento dinâmico ou dependências (ex.: irrigação afetando o estado).

- **Árvore de Manga**: Planta que cresce em etapas, dependente de irrigação e tempo.
  - Implementação: Prefab com modelo `.fbx` (exportado do `.blend` em `dripsim_assets`), script `PlantGrowth` (de `PlantSystem.cs`) para escalar o modelo e adicionar frutas via partículas ou sub-objetos. Animação de crescimento com Animator.

- **Videira de Uva**: Similar à manga, mas com mecânica de espalhamento (vinhas crescendo lateralmente).
  - Implementação: Prefab com mesh deformável (usando Vertex Animation ou shader URP), script para crescimento procedural baseado em água, e colheita interativa (clique para coletar uvas como itens).

- **Bomba de Irrigação**: Equipamento para puxar água de um rio simulado, com som e animações.
  - Implementação: Prefab com modelo animado (Blender rig), script para ativar física (Rigidbody para vibração) e som (AudioSource), integrado a `IrrigationSystem.cs` para reabastecimento automático.

- **Animais de Fazenda (ex.: Galinhas ou Abelhas para Polinização)**: Props opcionais para ecossistema, que interagem com plantas.
  - Implementação: Prefab com AI simples (NavMeshAgent para movimento), animações (andar, bicar), e dependência de irrigação (animais fogem de áreas secas). Use DOTS para otimização se houver muitos.

### Considerações Gerais
- **Ordem de Complexidade**: Comece implementando os de baixa complexidade para ambientar a cena, depois adicione interações médias, e finalize com os altos para mecânicas refinadas.
- **Implementação no Unity**:
  - Use prefabs em `dripsim_game/Assets/Prefabs` para reutilização.
  - Modelos: Crie em Blender (`dripsim_assets/*.blend`), exporte como `.fbx` para Unity.
  - Visuais: Aplique shaders URP para efeitos semiáridos (ex.: poeira, mudança de cor com irrigação).
  - Scripts: Integre com os existentes – ex.: `PlantSystem.cs` para plantas dependentes de `IrrigationSystem.cs`.
- **Otimização**: Para props altos, use LOD (Level of Detail) e occlusion culling para performance, especialmente com URP.
- **GitHub**: Como o repositório é público, adicione novos props e commits (ex.: "Adiciona prefab de gotejador"). O README já menciona os scripts, então atualize-o se adicionar mais detalhes.
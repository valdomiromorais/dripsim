# DripSim - Simulador de Fazenda 3D

**DripSim** é um simulador de fazenda 3D desenvolvido no Unity 3D com C#, ambientado na região semiárida do sub-médio São Francisco. O foco do jogo é a fruticultura irrigada, com ênfase no cultivo de manga e uva, e a gestão de um sistema de irrigação por gotejamento. O projeto utiliza o Universal Render Pipeline (URP) para gráficos otimizados e está em desenvolvimento.

## Estrutura do Repositório

- **dripsim_game/**: Projeto Unity, contendo:
  - `Assets/`: Scripts C# (ex.: `PlayerController.cs`, `IrrigationSystem.cs`, `PlantSystem.cs`), cenas, prefabs, materiais, e outros recursos do jogo.
  - `ProjectSettings/`, `Library/`, etc.: Arquivos de configuração do Unity (não versionados).
- **dripsim_assets/**: Recursos brutos, como modelos 3D (`.blend`, `.fbx`), texturas (`.png`, `.jpg`), e áudio (`.mp3`, `.wav`).
- **dripsim_docs/**: Documentação do projeto, incluindo PDFs e arquivos de texto (ex.: `ProjectInstructionsGrok.txt`).
- **folder_content.txt**: Lista da estrutura do diretório.
- **.gitignore**: Ignora arquivos temporários do Unity e ferramentas de arte (ex.: `.csproj`, `.blend1`).
- **.gitattributes**: Configura o Git LFS para arquivos grandes (ex.: `.unity`, `.blend`, `.psd`).

## Pré-requisitos

- **Unity**: Versão 2022.3 ou superior (compatível com URP).
- **Git**: Para controle de versão.
- **Git LFS**: Para gerenciar arquivos grandes (modelos 3D, texturas, etc.).
- **Blender** (opcional): Para editar modelos `.blend` em `dripsim_assets`.
- **IDE**: Visual Studio, Rider, ou outra para editar scripts C#.

## Configuração

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu-usuario/dripsim.git
   cd dripsim
   ```

2. **Instale o Git LFS**:
   ```bash
   git lfs install
   git lfs pull
   ```

3. **Abra o projeto no Unity**:
   - Abra o Unity Hub.
   - Adicione o projeto apontando para `dripsim/dripsim_game`.
   - Certifique-se de que o Universal Render Pipeline (URP) está configurado em `Project Settings > Graphics`.

4. **Teste a cena inicial**:
   - Abra `dripsim_game/Assets/Scenes/SampleScene.unity`.
   - Configure os scripts `PlayerController.cs`, `IrrigationSystem.cs`, e `PlantSystem.cs` no Inspector, se necessário.

## Como Contribuir

1. Crie um fork do repositório e clone-o localmente.
2. Crie um branch para sua feature: `git checkout -b nome-da-feature`.
3. Faça commits descritivos: `git commit -m "Adiciona feature X"`.
4. Envie para o GitHub: `git push origin nome-da-feature`.
5. Abra um Pull Request no repositório original.

## Licença

A definir. (Recomenda-se a licença MIT para projetos de código aberto.)
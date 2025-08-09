# DripSim – 3D Farm Simulator

**DripSim** is a 3D farm simulator developed in Unity 3D with C#, set in the semi-arid region of the Sub-Middle São Francisco River. The game focuses on irrigated fruit farming, emphasizing mango and grape cultivation, and the management of a drip irrigation system. The project uses the Universal Render Pipeline (URP) for optimized graphics and is currently in development.

## Repository Structure

- **dripsim_game/**: Unity project, containing:
  - `Assets/`: C# scripts (e.g., `PlayerController.cs`, `IrrigationSystem.cs`, `PlantSystem.cs`), scenes, prefabs, materials, and other game assets.
  - `ProjectSettings/`, `Library/`, etc.: Unity configuration files (not versioned).
- **dripsim_assets/**: Raw assets such as 3D models (`.blend`, `.fbx`), textures (`.png`, `.jpg`), and audio files (`.mp3`, `.wav`).
- **dripsim_docs/**: Project documentation, including PDFs and text files (e.g., `ProjectInstructionsGrok.txt`).
- **folder_content.txt**: List of the directory structure.
- **.gitignore**: Ignores Unity and art tool temporary files (e.g., `.csproj`, `.blend1`).
- **.gitattributes**: Configures Git LFS for large files (e.g., `.unity`, `.blend`, `.psd`).

## Prerequisites

- **Unity**: Version 2022.3 or higher (URP-compatible).
- **Git**: For version control.
- **Git LFS**: To handle large files (3D models, textures, etc.).
- **Blender** (optional): To edit `.blend` models in `dripsim_assets`.
- **IDE**: Visual Studio, Rider, or another C# editor.

## Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/dripsim.git
   cd dripsim
   ```

2. **Install Git LFS**:
   ```bash
   git lfs install
   git lfs pull
   ```

3. **Open the project in Unity**:
   - Launch Unity Hub.
   - Add the project pointing to `dripsim/dripsim_game`.
   - Make sure the Universal Render Pipeline (URP) is configured under `Project Settings > Graphics`.

4. **Test the initial scene**:
   - Open `dripsim_game/Assets/Scenes/SampleScene.unity`.
   - Assign `PlayerController.cs`, `IrrigationSystem.cs`, and `PlantSystem.cs` to the Inspector if needed.

## Contributing

1. Fork the repository and clone it locally.
2. Create a branch for your feature:  
   ```bash
   git checkout -b feature-name
   ```
3. Make descriptive commits:  
   ```bash
   git commit -m "Add feature X"
   ```
4. Push to GitHub:  
   ```bash
   git push origin feature-name
   ```
5. Open a Pull Request to the original repository.

## License

To be defined. (MIT License is recommended for open-source projects.)

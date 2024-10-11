# Game Cheats
This repository was made for the [Arisen Studio](https://github.com/ohhsodead/arisen-studio) project.

It contains cheat files for PlayStation 3 and Xbox 360 games. Each folder contains game files with cheat codes, offsets, and values for various game versions.

## Folder Structure
- `PS3/` - Contains cheat files for PlayStation 3 games.
- `XBOX360/` - Contains cheat files for Xbox 360 games.

Each game file is formatted in JSON, and includes cheat information such as offsets, opcodes, and values for different regions and versions.

## How to Add Your Own Mods or Offsets

To add your own mods or offsets to the existing files, follow these steps:

1. **Find the correct file:**
   - Navigate to the appropriate folder (`PS3` or `XBOX360`).
   - Select the file corresponding to the game, region, and version you want to modify.

2. **Edit the file:**
   - Open the file in a text editor.
   - Locate the `"Cheats"` section, which contains all the mods/cheats for that game.

3. **Add a new mod:**
   - Use the following format to add a new mod or offset:

   ```json
   {
     "Name": "Your Mod Name",
     "Offsets": [
       {
         "DataType": "int32",  // Data type (e.g., int32, float, etc.)
         "Offset": "00000000", // Memory address or offset
         "Opcode": "00000000", // Opcode (if applicable)
         "Value": "00000000",  // Value to apply
         "ValueType": "int32"  // Value type
       }
     ]
   }
   ```

4. **Example:**
   Here's an example of adding a new mod for "Max Money":

   ```json
   {
     "Name": "Max Money",
     "Offsets": [
       {
         "DataType": "int32",
         "Offset": "001A779C",
         "Opcode": "00002000",
         "Value": "60000000",
         "ValueType": "int32"
       }
     ]
   }
   ```

5. **Save your changes:**
   - After adding your new mod/offset, save the file.

6. **Contribute your changes (optional):**
   - If you want to share your mods with others, you can fork the repository and submit a pull request with your changes.

---

## How to Add a New Game File

If the game you want to add mods for doesn't already exist in the repository, follow these steps to create a new game file:

1. **Navigate to the correct folder:**
   - For PlayStation 3 games, go to the `PS3` folder.
   - For Xbox 360 games, go to the `XBOX360` folder.

2. **Create a new JSON file:**
   - Name the file using the following format:  
     `GameTitle_Region_Version.json`  
     (e.g., `Bioshock_2_JP_BLJS10078_01.03.json`)

3. **Add the basic file structure:**
   - Copy and paste the structure below into the new file:

   ```json
   {
     "Game": "Game Title",           // Replace with the game's title
     "Region": "Region Code",        // Replace with the game's region code (e.g., BLJS10078)
     "Version": "Game Version",      // Replace with the game's version number (e.g., 01.03)
     "Cheats": [
       {
         "Name": "Mod Name",         // Replace with the mod or offset name
         "Offsets": [
           {
             "DataType": "int32",   // Data type (e.g., int32, float, etc.)
             "Offset": "00000000",  // Memory address or offset
             "Opcode": "00000000",  // Opcode (if applicable)
             "Value": "00000000",   // Value to apply
             "ValueType": "int32"   // Value type
           }
         ]
       }
     ]
   }
   ```

4. **Fill in the game details:**
   - Replace the placeholder text (`Game Title`, `Region Code`, `Game Version`, etc.) with the actual information for the game.
   - Add as many mods or offsets as needed in the `"Cheats"` section.

5. **Example:**
   Here's an example for "Bioshock 2 JP":

   ```json
   {
     "Game": "Bioshock 2 JP",
     "Region": "BLJS10078",
     "Version": "01.03",
     "Cheats": [
       {
         "Name": "Infinite Ammo & Items",
         "Offsets": [
           {
             "DataType": "int32",
             "Offset": "001DE03C",
             "Opcode": "00002000",
             "Value": "60000000",
             "ValueType": "int32"
           }
         ]
       },
       {
         "Name": "Max Money",
         "Offsets": [
           {
             "DataType": "int32",
             "Offset": "001A779C",
             "Opcode": "00002000",
             "Value": "60000000",
             "ValueType": "int32"
           }
         ]
       }
     ]
   }
   ```

6. **Save the file:**
   - Once you've added the details and cheats, save the JSON file in the appropriate folder (`PS3` or `XBOX360`).

7. **Contribute your new file (optional):**
   - If you'd like to share the new game file with others, submit a pull request with your newly created file.

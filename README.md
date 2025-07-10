# jawi-khat
Generating jawi khat dataset with additional complimentary Jawi character from existing Arabic font file. 

Step by step updating .tff font file to add external
Jawi character, which include the front, medial and final. 

Installation pre-requisite: FontForge

Part 1: Create new character
1. Open FontForge > Choose the `.tff` font file you have downloaded.
2. Check whether the character you want to add has it's own unicode or not. 
3. In this case we take Jawi "pa" character to be added in
Thuluth font. 
4. For "pa" there is already unicode for it which is `U+06A4`
5. Then find the nearest Jawi character to "pa", which is "fa" in Arabic. 
6. Copy the character and paste into the empty square below "pa" character"
7. Edit the font by adding another 2 dots. To do this, click Edit > Unlink Reference
8. Highlight the dot > Ctrl C > Ctrl V. The new dot will exist on top of the copied one. You can move it using Shift + direction
9. Once completed, Ctrl + s to save.

Part 2: Rename
1. For Arabic and Jawi, certain words has initial, middle and final position of character.
2. Hence, for "pa" we need to create the initial, middle and final position character too.
3. To create this, first go to Encoding > Add encoding slots.
4. Write 3 so we can create 3 empty slots for this.
5. It will bring you to the bottom of the page, where the character will have question mark as the name.
6. Now, find initial, middle and final character from "fa" and paste it into the new empty slots. Similarly add 2 more dots for it.
7. Now, we need to rename the character (or it called glyph). We need to establish a suffix for the name
   - **.init** - for initial / front character
   - **.medi** - for middle character
   - **.fina** - for final / back character
8. Now click the front "fa" and edit the name as `uni06A4.init`. Same goes to middle and final, use the above suffix.

Part 3: Link and lookup
1. After completed renaming, click Font Info > Lookup.
2. You will see 'init', 'medi' and 'fina' in GSUB page. This is already exist.
3. Click the  [+] button for 'init' first, it will pop down the subtable words. Click and and you will see the Edit data button on the right side will ungrey.
4. Click Edit data. You will see a lookup table that will tell the isolated word and its own positional word.
5. At the bottom of the dialogue, there is an empty space at the right of the Default Using Suffix button. Write `init` as the value.
6. Then click Default Using Suffix. It will the font that you name it's suffix as `.init ` will be added to the table. You can hover if you are in doubt.
7. Do this for `medi` and `fina` too.
8. Everytime you add new positional character, you need to update the lookup table by clicking Default Using Suffix button.

Useful Shortcut
- Ctrl + Shift + > : Find glyph
- Ctrl + u : Unlink reference (ungroup dot(s) from character)
- Ctrl + i : Glyph info

Unicode refernce:
| Character | Glyph | Unicode |
| ----------| ------ | ---------- |
| pa | ڤ | U+06A4 | 
| nga | ڠ	 | U+06A0 | 
| va | ﯛ | U+06CF | 
| nya | ڽ | U+06BD | 
| ga | ڬ | U+06AC | 

Test phrase:
ڤاڤيڤڤ ڬاݢيڬڬ ڠاڠيباڠ ۏاۏيۏڤ ڽاڽيڽيو


# Todo
1. Update font file
- [x] Thuluth
- [ ] Naskh
- [ ] Riqaa
- [ ] Nastaliq
- [ ] Diwani
- [ ] Kufi
- [ ] Amiri

2. Generate dataset
- [ ] Thuluth
- [ ] Naskh
- [ ] Riqaa
- [ ] Nastaliq
- [ ] Diwani
- [ ] Kufi
- [ ] Amiri


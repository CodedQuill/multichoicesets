# multichoicesets
Example code for creating multiple choices on a single page in ChoiceScript projects

# — DOCUMENTATION / USER GUIDE —

1. Copy the choice_set into the folder with the rest of your game files.

2. Rename the file to fit the theme of the set of choices, such as *'character_clothing_choiceset'*

3. Change the values in the corresponding Array to those you wish to use.

4. In the choiceset scene file, change the names of the sets. These are the words on the same line as the **choice* command. These will be displayed as 'selecting a/an your_choiceset_name'

5. Use *'*gosub_scene your_file_name start'* to present the choiceset to the player.

6. The return variables e.g. *'return_a'*, will be prefilled with the resulting text from the array. You can use these directly in the text, use them to parse an if-else block, or set them into other variables which are easier to remember e.g. *'set plyr_hair_col return_a'*.

# — ADVANCED —

6. To send the results of the choices directly to specific variables, go to the very bottom of the scene file. In the subroutine *'write'* will be a handful of '*set*' commands. Simply change the variable name to wherever you want it to go, such as a created variable in startup.

7. If you wish to use the raw number values from the choiceset then you can edit the *'write'* subroutine to handle the params differently. This may be especially handy if you wish to use multi-replace to parse responses, or perform number operations such as if setting/modifying stats.

8. The example set up includes four options per choiceset. If you wish to add or remove options, you will need to amend the code in the file. 
*line_break
— To remove options, you can create a **temp in_use false* variable at the top of the file after the label *'start'* then *ctrl+f* to find every instance of the option to remove and add **if(in_use)* to the start of the line. 
*line_break
— For example, select the option line containing *'charlie[3]'*, *ctrl+f*, replace with *'*if(in_use)' + the rest of the original option line*, this will mean all charlie-level third options will not be presented to the player. 
*line_break
— Adding options requires a lot of copy and pasting into each choices, and amending the range of values sent to the subroutine *'write'* at the end of each file. This is tedious, with a high potential for errors. The player is also unlikely to appreciate scrolling through reams of options. Personally, I would recommend you find another solution.

9. If you wish to use the same size of choiceset again, follow the steps as above, but now you will need to create a second array in the same format as the first.
*line_break
— You will also need to amend every entry in the choiceset scene file to the new arrays' names. This can be done easily using find and replace. For example, to change all *'alpha3' ctrl+f*, then replace all with *'hair3'*. This will also change the *gosub write*, at the bottom of the file.
*line_break
— All values will still be returned to *'return_a', 'return_b', etc…* unless otherwise specified in the *'write'* subroutine.

# — Questions and Suggestions —

If you have any questions about, or suggestions on how to improve, this resource, feel free to contact me on the forum.

Thanks.

*CodedQuill*

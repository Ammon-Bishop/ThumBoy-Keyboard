I made a video about the process that you can watch here:
https://www.youtube.com/@Drastic_Dev

I did something tacky with the pcb; i had an edge that was supposed to be straight that was actually made of very slightly angle-varying lines because i had positioned the mcu and power switch using either a 1mm, .5mm, or .25mm grid i think. point is, dont do this yourself when designing a keyboard. in addition my point is it would be nice if someone brave were to fab these pcbs and build the board and confirm whether it fits inside the case printed with the files provided (it really should; i was only off by probably .004mm max. mine should even fit; may have to sand it, though.) i designed the case files that are on this repo to work with the version of the pcb that has that edge as perfectly straight and has the mcu and power switch positioned perfectly, to the .001mm. to be clear, there shouldnt be any problems with the cases and pcbs on this repo, just want to give fair warning that i havent physically tested the exact pcb geometries on this repo with the case files on this repo.
will update this readme when someone has confirmed and has let me know.
- in addition, with the pcb, i drew the edge cuts by hand using snapping to probably a 1mm grid on kicad, so the edge cuts are probably not spaced the same distance from the edges of the keycaps in all spots. if that matters to you, you are welcome to (for each side of the keyboard, because the two sides are not perfectly mirrored) paste my config into ergogen.ceoloide.com and create a keycaps outline in the config and download the dxf file for that outline and use your choice of 2D CAD software to offset the keycaps' edges by your desired amount (i believe the edge cuts you will create by pasting this outline into KiCad {pasting the offset outline from the 2D CAD software into KiCad} will need to pass the design rules checker {Kicad DRC}), then basically just connect the lines (that you just created by offsetting) into one outline. this will create a "dxf version" of your desired KiCad Edge.Cuts layer that is identically offset from the edges of keycaps, just like you wanted. now just export your CAD project to a dxf file and import that into KiCad and find a way to position it perfectly. To put that in simple terms:
1. paste in my config.yaml code to ergogen.ceoloide.com
2. navigate to the "outlines" section
3. copy the code that makes the outline named "right_outline"
4. paste it in the outlines section (gives error, dont worry about it)
5. rename it to whatever you want (ideally something along the lines of right_keycaps); this will fix the error and make a separate outline identical to right_outline
6. edit the first value in the "size" property to 18mm (width of choc keycap) and the second value to 17mm (height of choc keycap)
7. download [name of outline you just created in step 5].dxf (by clicking green download button)
8. in KiCad, navigate to File -> Import
9. import your dxf file
10. position it perfectly
11. now you have better edge cuts!

also, ik there is no reset switch routing in the pcb traces; im probs gonna leave that as-is because i believe zmk has a reset feature that you can code into a keypress in the firmware (meaning i believe you can have a reset key in your keyboard layout rather than another physical component you would have to add; a reset key instead of a reset switch)


-----config.yaml files clarifications-----

i did not end up using left_outline.dxf and right_outline.dxf, but you can learn from the code that creates them in the config. the reason i didn't use the outlines there is i manually drew my edge cuts for the two pcbs

--end of config.yaml files clarifications--

this was my first keyboard design, so lmk if anything else can be improved and i will look into it. should be ready to print/fabricate and use, but you might want to make it "more perfect" a precision case outline.
enjoy!



.... Last Updated: 6th of January, 2025 at 07:12 ....

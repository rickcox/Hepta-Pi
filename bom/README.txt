
BOM/CPL Procedure 30Nov2021
directory reference is boards/

IN KICAD
1) From the Schematic editor run: Schematic editor, Tools, "Generate BOM".  
     my-kicad-plugins/rick_bom/rick_bom_csv_grouped_by_value_with_fp.py
   Generates an xml netlist in the proj dir and extensive bom in proj_dir/bom.
   The bom result may be used for manual work, but is ignored in this workflow
2) From the PCB Editor run: File, Fabrication Outputs, Component Placement
   set Output:bom, Format:CSV, Units:Millimeters, File: Single file 
   This writes a generic cpl file to proj_dir/bom.
3) Now is a good time to generate gerbers and drill files to gerbers/
   And reports to doc/

AT COMMAND LINE
4) Run my-kicad-plugins/jlc-kicad-tools -v ./4pi-Farm_2.5 \
	-o ./4pi-Farm_2.5/jlcpcb | tee jlcpcb/jlc-kicad-tools.log
   ( pip install git+https://github.com/matthewlai/JLCKicadTools )

   This:
   - Reads the xml netlist to access all of the component info
   - Reads the cpl files to get component locations, orientation, and side
     (rotation exceptions@ ~/.local/lib/python*/site_packages/jlc-kicad-tools/)
   - Writes bom_jlc and cpl_jlc files to the jlcpcb/ directory
5) Manual post-edits:
   - Strip off the back side components from cpl - No support for 2-sided assy
   - Things to review/edit in the BOM/CPL:
     o Add in the Pi4CM 100 pin connectors to bom
     o Create a mini-bom for jlcpcb assembly with stuff removed:
     o Delete any through hole components from mini-bom
       unless you want to pay for hand assy
     o Delete any components from mini-bom you want to hand assemble later
     o LCSC Part numbers in BOM - Check - are they current and available, 
       and Basic rather than Extended parts if possible?
       You get a chance to edit this again once entered into jlcpcb's system
6) zip up the gerber files prior to submitting   


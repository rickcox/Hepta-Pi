# export with Protel File Naming

# recommend to write all layers out from KiCad,
# then only put what the PCB manufacturer want into the zip

DESIGN='Hepta-Pi_1.1'
rm -f  ${DESIGN}.zip
zip    ${DESIGN}.zip \
	${DESIGN}*-Edge_Cuts* \
	${DESIGN}*_Cu* \
	${DESIGN}*_Mask* \
 	${DESIGN}*_Paste* \
	${DESIGN}*_Silkscreen* \
	${DESIGN}*.drl

#mv 4pi-Farm_2.51-Edge_Cuts.gm1 4pi-Farm_2.51-Edge_Cuts.gko
#mv 4pi-Farm_2.51-In1_Cu.g2 4pi-Farm_2.51-In1_Cu.g2l
#mv 4pi-Farm_2.51-In2_Cu.g3 4pi-Farm_2.51-In2_Cu.g3l
#mv 4pi-Farm_2.51.drl 4pi-Farm_2.51.xln



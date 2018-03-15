MODFLOW name file template
==========================

This document is prepared for the readers with knowledge of MODFLOW to create the MODFLOW name file template used by ``SUSTAIN``.
A MODFLOW name file template, *'mf_template.nam'*, should be placed in the master directory.
The template is used to reconstruct the MODFLOW name file for the scenario run (with pumping/recharge changes).
Note that this file should be constructed based on the original baseline MODFLOW name file with some packages being removed. All the file path is relative to the master directory.
The changes in the scenario run are implemented through the MODFLOW ``Well`` package. Therefore, the template must **not** contain the Well package.
Other outputs such as the List file, groundwater head and drawdown files, and the cell-by-cell water budget file will be re-written and therefore must not be included in the template.
However, these files, especially their file numbers, need to be specify in the ``SUSTAIN`` name file (See :doc:`../files/name`.).

Example MODFLOW name file template
----------------------------------

Below is an example of the MODFLOW name file template.
The ``WEL`` package is removed because it will be created by ``SUSTAIN``.
Several outputs are also removed from this name file because they will be written to the new output directory.
These outputs include the List file, groundwater head and drawdown files, and the cell-by-cell water budget file.
The ``SUSTAIN`` namefile will control the locations of these new files.

::

  # This is a MODFLOW name file template for NeDNR SUSTAIN
  BAS6  1 modflow\UNW14-T_refSShd.bas
  DIS  29 modflow\UNW14_jg0516rev_1L20ft2L100_tr.dis
  LPF  11 modflow\UNW16-T_zon.lpf
  ZONE 40 modflow\UNWjgKzon3.zone
  DRN  13 modflow\UNW14-T_param.drn
  RIV  14 modflow\UNW14-T.riv
  EVT  20 modflow\UNW14-T_szigNewSurf6_7.evt
  GHB  17 modflow\UNW_TrBBcells_decrCond0702.ghb
  OC   22 modflow\20120613_2TSall.oc
  PCG  19 modflow\UNW14-T.pcg
  STR  27 modflow\UNWjg_param_TrSeg3Rev1.str
  RCH  18 modflow\UNWv10_wcanal_ashley_div25.RCH
  DATA(BINARY) 33 modflow\SS_PLAY_sim102.hds

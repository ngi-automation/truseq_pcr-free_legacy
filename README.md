# Automated TruSeq PCR-free Installation Guide #
**For Agilent NGS Workstation Option B**

## Contents ##
1. [Description](#Description)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Protocol](#protocol)
5. [License](#license)

## Description ##
This document describes how to set up the automated TruSeq PCR-free protocol for the Agilent NGS Workstation option B created at NGI Stockholm. This version of the PCR-free protocol is not in use anymore at NGI but has since long been replaced by a version that utilise our custom extended Bravo configuration. Therefore it does not contain any of the optimisations and improvements made since.

## Requirements ##

Item                                 | Note
:------------------------------------|:---------
Agilent NGS Workstation              | :warning: Option B configuration only
Eppendorf twin.tec 96 PCR plate      | Eppendorf, cat# 0030 128.672 (int); 951020460 (US)
Nunc deepwell 1.3 mL plate           | Thermo Scientific, cat# 260251
ABgene 2.2 mL storage plate Mk.II    | Thermo Scientific, cat# AB-0933
Deepwell plate adaptor on position 6 | Agilent Technologies, cat# G5498B#012
Labware definitions                  | Provided in `all_labware_liquids.vzp`
Liquid classes definition            | Provided in `all_labware_liquids.vzp`

\* provided in `all_labware_liquids.vzp`

#### Included files ####
```
illumina_double-spri.pro
illumina_spri.pro
truseq_nano_pcr.pro
truseq_pcr-free.VWForm
truseq_pcr-free.js
truseq_pcr-free.rst
truseq_pcr-free_cleanup.rst
truseq_pcr-free_ligation.pro
truseq_pcr-free_reaction.pro
truseq_pcr-free_setup1.pro
truseq_pcr-free_setup2.pro
truseq_pcr-free_setup3.pro
truseq_pcr-free_setup4.pro
truseq_pcr-free_setup5.pro
truseq_pcr-free_setup6.pro
truseq_pcr-free_setup7.pro
all_labware_liquids.vzp
resources/clear_inventory.bat
resources/1313497517_media_controls_light_play.png
resources/clear_inventory.sql
resources/1313497192_media_controls_light_pause.png
```

## Installation ##
### Download files ###

##### Using Git #####
Clone into `https://github.com/ngi-automation/truseq_pcr-free_legacy.git` from the `Protocol Files` directory:

```bash
cd "C:\VWorks Workspace\Protocol Files"
git clone https://github.com/ngi-automation/truseq_pcr-free_legacy.git
```

Alternatively, download the compressed folder from:
[`https://github.com/ngi-automation/truseq_pcr-free_legacy/archive/master.zip`][zip]
and extract to `C:\VWorks Workspace\Protocol Files`. Rename the resulting `truseq_pcr-free_legacy-master` folder to `truseq_pcr-free_legacy`. The path to the folder containing the extracted files should then be `C:\VWorks Workspace\Protocol Files\truseq_pcr-free_legacy`.

### Configure ###
#### Labware and and liquid class definitions ####
Use the import feature in VWorks from `File › Import`in the toolbar and select the `all_labware_liquids.vzp` file included. See the [VWorks Knowledge Base][import] for more information.

#### Device files ####

Device files and profiles are system specific and will not be provided. The "standard" Bravo configuration is used in the TruSeq PCR-free protocols:

##### Standard configuration #####
Position | Type | Part#
-------: | ---- | -----
1&ndash;3, 8  | Deck Platepad | `G5498b#004`
4, 6     | Peltier Thermal Station (Inheco) | `G5498b#021`
5        | Orbital Shaking Station | `G5498b#033`
7        | Magnetic Bead Accessory | `G5498b#008`
9        | Thermal Station (ThermoCube) | `G5498b#036`/`7`/`8`

For reference see Agilent's [accessories catalog][catalog] for the Bravo.

Each `.pro` file must have the correct device file set:

See the [VWorks Knowledge Base][device-file] for more information on how to select the device file.

## Protocol ##

An abridged version of the old NGI Stockholm/SciLifeLab SOP can be accessed [here][sop] and should contain the neccessary instructions to set up and run the robot protocol.

## License ##
> Licensed under the Apache License, Version 2.0 (the "License");
> you may not use this file except in compliance with the License.
> You may obtain a copy of the License at
> 
> http://www.apache.org/licenses/LICENSE-2.0
>
> Unless required by applicable law or agreed to in writing, software
> distributed under the License is distributed on an "AS IS" BASIS,
> WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
> See the License for the specific language governing permissions and limitations under the License.

The full license can also be found in the file LICENSE and must included when redistributing the software.

If this method is used to generate results for publication we ask that you include a reference to this repository, something like:
```
Automation protocols made available by the National Genomics Infrastructure Stockholm at https://github.com/ngi-automation/truseq_pcr-free_legacy
```
*VWorks Automation Control*, *Bravo* and other things relating to the *Agilent NGS Workstation* are trademarks owned by Agilent Technologies, Inc. (Santa Clara, CA 95052-8058, US).

*TruSeq PCR-free* is a trademark owned by Illumina, Inc. (San Diego, CA 92122 US).

[email]: mailto:joel.gruselius@scilifelab.se "E-mail author"
[ngi]: https://www.scilifelab.se/facilities/ngi-stockholm/ "NGI Stockholm"
[scilife]: https://www.scilifelab.se "SciLifeLab"
[zip]: https://github.com/ngi-automation/truseq_pcr-free_legacy/archive/master.zip
[import]: http://www.velocity11.com/techdocs/AutomationSolutionsKB/vworks4_ug/11_Troubleshooting.15.03.html#2005458
[catalog]: http://www.chem.agilent.com/Library/catalogs/Public/5991-0369EN.pdf
[sop]: https://drive.google.com/open?id=1P0EqELMU-faXRcIpwR1sb1q1AKJ0IsdN
[device-file]: http://www.velocity11.com/techdocs/AutomationSolutionsKB/vworks4_ug/02_CreateProtocolBasic.04.08.html#1981042

---

>[National Genomics Infrastructure][ngi] at [SciLifeLab][scilife]  
<joel.gruselius@scilifelab.se>  
2019-05-24

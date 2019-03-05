---
title: Deyimler Özeti
ms.date: 11/04/2016
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
ms.openlocfilehash: 76a549de7791f8af36fbf150c19cf6ed0de2cbe6
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152761"
---
# <a name="summary-of-statements"></a>Deyimler Özeti

*deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Etiketli deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bileşik deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Seçimi deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yineleme deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atlama-deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try haricinde deyimi*  / \* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-finally deyimi*  / \* Microsoft Specific \*/

*atlama-deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**goto** *tanımlayıcı* **;**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam edin.**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**BREAK;**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dönüş** *ifade*<sub>iyileştirilmiş</sub> **;**

*Bileşik deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *bildirim listesi*<sub>iyileştirilmiş</sub> *deyim listesindeki*<sub>iyileştirilmiş</sub> **}**

*bildirim listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim listesi* *bildirimi*

*ifade listesinin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade listesinin* *deyimi*

*ifade deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade*<sub>iyileştirilmiş</sub> **;**

*Yineleme deyiminin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sırada (**  *ifade*  **)**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**yapmak** *deyimi* **sırada (***ifade***);**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**için (** *ifade*<sub>iyileştirilmiş</sub> **;** *ifade*<sub>iyileştirilmiş</sub> **;** *ifade*<sub>iyileştirilmiş</sub> **)** *deyimi*

*Seçimi deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (** *ifade* **)** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (** *ifade* **)** *deyimi* **başka** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**geçiş (** *ifade* **)** *deyimi*

*Etiketli deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* **:** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Servis talebi** *sabit-ifade* **:** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan:** *deyimi*

*try haricinde deyimi*: /\* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *compound-statement* **__except (** *ifade* **)** *bileşik deyim* 

*try-finally deyimi*: /\* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *compound-statement* **__finally** *bileşik deyim* 

## <a name="see-also"></a>Ayrıca bkz.

[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)

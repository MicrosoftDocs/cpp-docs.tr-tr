---
title: Deyimler özeti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e83d4db17dd20a46ed2cbdd91598428e14748cf0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030319"
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
&nbsp;&nbsp;&nbsp;&nbsp;**goto***tanımlayıcı***;**<br/>
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
&nbsp;&nbsp;&nbsp;&nbsp;**sırada (***ifade***)***deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**yapmak***deyimi***sırada (***ifade***);**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**için (***ifade*<sub>iyileştirilmiş</sub> **;** *ifade*<sub>iyileştirilmiş</sub> **;** *ifade*<sub>iyileştirilmiş</sub> **)** *deyimi*

*Seçimi deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (***ifade***)***deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (***ifade***)***deyimi***başka***deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**geçiş (***ifade***)***deyimi*

*Etiketli deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı***:***deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Servis talebi***sabit-ifade***:***deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan:***deyimi*

*try haricinde deyimi*: /\* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try***compound-statement* **__except (***ifade***)***bileşik deyim* 

*try-finally deyimi*: /\* Microsoft Specific \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try***compound-statement* **__finally***bileşik deyim* 

## <a name="see-also"></a>Ayrıca Bkz.

[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)
---
title: Deyimler Özeti
ms.date: 11/04/2016
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
ms.openlocfilehash: 1a230ca7d998316d2ec96e76b54ac60575acd2ee
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857001"
---
# <a name="summary-of-statements"></a>Deyimler Özeti

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*etiketli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bileşik ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade* ifadesi<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*seçim-ekstresi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yineleme-ekstresi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıçrama-deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-except-deyimin* /\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-finally-deyimin* /\* Microsoft 'a özgü \*/

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**goto** *tanımlayıcı* **;**<br/>
&nbsp;&nbsp;&nbsp;**devam** &nbsp;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kesme;**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Return** *ifadesi*<sub>opt</sub> **;**

*bileşik ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

*bildirim-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi-List* *bildirimi*

*Ekstre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*açıklaması*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade-List* *deyimidir*

*ifade ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade*<sub>katılımı</sub> **;**

*yineleme-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sırada (**  *ifade*  **)**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**yapmak** *deyimi* **sırada (** *ifade* **);**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**için (** *ifade*<sub>iyileştirilmiş</sub> **;** *ifade*<sub>iyileştirilmiş</sub> **;** *ifade*<sub>iyileştirilmiş</sub> **)** *deyimi*

*seçim-ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (** *ifade* **)** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (** *ifade* **)** *deyimi* **başka** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**geçiş (** *ifade* **)** *deyimi*

*etiketli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* **:** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Servis talebi** *sabit-ifade* **:** *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan:** *deyimi*

*try-except-deyimin*:/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__except (** *ifade* **)** *bileşik deyim*

*try-finally-deyimin*:/\* Microsoft 'a özgü \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__finally** *bileşik deyim*

## <a name="see-also"></a>Ayrıca bkz.

[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)

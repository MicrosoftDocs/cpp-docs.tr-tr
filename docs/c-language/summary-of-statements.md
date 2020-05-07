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
&nbsp;&nbsp;&nbsp;&nbsp;*Etiketli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bileşik ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*seçim-ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yineleme-ekstresi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıçrama-deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-except-ekstre*  / \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-finally-deyimin*  / \* Microsoft 'a özgü\*/

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**goto***tanıtıcıya*git **;**    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sonundan**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Return** *ifadesi*<sub>opt</sub> **;**

*bileşik ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-List*<sub>opt</sub> *bildirimini-List*<sub>opt</sub> **}**

*bildirim-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bağımsız*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-liste* *bildirimi*

*Ekstre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre-List* *ekstresi*

*ifade ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade*<sub>katılımı</sub> **;**

*yineleme-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**while (**  *ifade*  **)**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Do**  *deyimi*  **while (**  *ifade*  **);**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**for (**  *Expression*<sub>opt</sub> **;** *Expression*<sub>opt</sub> **;** *Expression*<sub>opt</sub> **)** *deyimi*

*seçim-ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**if (**  *ifade*  **)**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**IF (**  *Expression*  **)**  *deyimi*  **Else**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Switch (**  *ifade*  **)**  *deyimi*

*etiketli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*  **:**  *ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Case**  *sabiti-ifade*  **:**  *deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan:**  *ifade*

*try-except-deyimin*:/\* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try**  *bileşik deyim* **__except (**  *ifade*  **)**  *bileşik deyim*

*try-finally-deyimin*:/\* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try**  *bileşik deyimli* **__finally**  *bileşik ifade*

## <a name="see-also"></a>Ayrıca bkz.

[Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)

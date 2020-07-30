---
title: Deyimler Özeti
ms.date: 11/04/2016
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
ms.openlocfilehash: 122c79b53a8af8a384097dec51a14746a090b1cf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220801"
---
# <a name="summary-of-statements"></a>Deyimler Özeti

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Etiketli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bileşik ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*seçim-ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yineleme-ekstresi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıçrama-deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-except-deyimleri*  / \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*try-finally-deyimin*  / \* Microsoft 'a özgü\*/

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`goto`**  *tanımlayıcı*  **;**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sonundan**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`return`***ifade*<sub>katılımı</sub> **;**

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
&nbsp;&nbsp;&nbsp;&nbsp;**`do`**  *deyim*  **while (**  *ifade*  **);**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**for (**  *Expression*<sub>opt</sub> **;** *Expression*<sub>opt</sub> **;** *Expression*<sub>opt</sub> **)** *deyimi*

*seçim-ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**if (**  *ifade*  **)**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**if (***ifade***)***deyim* **`else`** *deyimi*          <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Switch (**  *ifade*  **)**  *deyimi*

*etiketli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*  **:**  *ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`case`**  *sabit ifade*  **:**  *deyim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan:**  *ifade*

*try-except-deyimin*:/ \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try**  *bileşik deyim* **__except (**  *ifade*  **)**  *bileşik deyim*

*try-finally-deyimin*:/ \* Microsoft 'a özgü\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try***bileşik ifade* **`__finally`** *bileşik-ekstresi*    

## <a name="see-also"></a>Ayrıca bkz.

[Tümcecik yapısı dil bilgisi](../c-language/phrase-structure-grammar.md)

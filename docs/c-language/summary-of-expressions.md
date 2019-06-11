---
title: İfadelerin Özeti
ms.date: 06/14/2018
ms.assetid: ed448953-687a-4b57-a1cb-12967bd770ea
ms.openlocfilehash: 320baa51d54f00ac4fdb6633922a8bb36cf92a94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157824"
---
# <a name="summary-of-expressions"></a>İfadelerin Özeti

*Birincil ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sabit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dize sabit değeri*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *ifade* **)**

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*expression*  **,**  *assignment-expression*

*Sabit ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*

*Koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-veya-ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-veya-expression* **?**  *ifade* **:** *koşullu ifade*

*atama ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unary-expression* *assignment-operator* *assignment-expression*

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Birincil ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **[** *ifade* **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **(** *bağımsız değişken ifade listesi*<sub>iyileştirilmiş</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **.**  *tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **->** *tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

*bağımsız değişken ifade listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*argument-expression-list*  **,**  *assignment-expression*

*Tekli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **++**  *Tekli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **--**  *Tekli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birli-işleç*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Cast ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sizeof** *tekli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sizeof (** *tür adı* **)**

*birli işleç*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **&** **&#42;** **+** **-** **~** **!**

*Cast ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tekli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *tür adı* **)** *atama ifadesi*

*ifade çarpma*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Cast ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade çarpma* **&#42;** *atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade çarpma* **/** *atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade çarpma* **%** *atama ifadesi*

*additive-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*additive-expression* **+** *çarpma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*additive-expression* **-** *çarpma ifadesi*

*Shift-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*additive-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-expression* **\<\<** *additive-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-expression* **>>** *additive-expression*

*İlişkisel ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **\<** *shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **>** *shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **\<=** *shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **>=** *shift-expression*

*Eşitlik ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eşitlik ifade* **==** *ilişkisel ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eşitlik ifade* **! =** *ilişkisel ifade*

*VE ifadeli*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eşitlik ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*VE ifade* **&** *eşitlik ifadesi*

*dışlamalı OR ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*AND ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dışlamalı OR ifadesi* **^** *ve ifade*

*OR ifadesi kapsamlı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dışlamalı OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OR ifadesi kapsamlı* **&#124;** *dışlamalı OR ifadesi*

*mantıksal-ve-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OR ifadesi dahil*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-ve-expression* **&&** *OR ifadesi dahil*

*mantıksal-veya-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-ve-ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression*  **&#124;&#124;**  *logical-AND-expression*

## <a name="see-also"></a>Ayrıca bkz.

- [Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)

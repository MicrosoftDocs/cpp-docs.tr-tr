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

*birincil ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dize sabit değeri*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(**  *ifade*  **)**

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade*  **,**  *atama ifadesi*

*sabit ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*

*koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MANTıKSAL or ifadesi*  **?**  *ifade*  **:**  *koşullu ifade*

*atama ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birli ifade* *atama-işleç* *atama-ifade*

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birincil ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **[**  *ifade*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **(**  *bağımsız değişken-ifade-List*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **.**  *Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **->**  *tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

*bağımsız değişken-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bağımsız değişken-ifade listesi*  **,**  *atama ifadesi*

*birli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**++**  *Birli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**--**  *Birli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Birli işleci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Cast ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sizeof**  *birli ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sizeof (**  *tür adı*  **)**

*birli-işleç*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**&****&#42;** **+**&#42;**-** **!** ! **~**

*Cast ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Birli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(**  *tür adı*  **)**  *Cast ifadesi*

*çarpma ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Cast ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma* ifadesi **&#42;** *Cast ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çoğulereptıcı-ifade*  **/**  *atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çoğulereptıcı-ifade*  **%**  *atama ifadesi*

*Toplamsal ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Adli ifade*  **+**  *çoğulereptive-ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Adli ifade*  **-**  *çoğulereptive-ifadesi*

*SHIFT ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Toplamsal ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-Expression***\<***toplamalı ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-Expression*  **>>**  *toplamalı ifadesi*

*ilişkisel ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*SHIFT ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade*  **\<**  *kaydırma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade*  **>**  *kaydırma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade***\<***kaydırma ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade*  **>=**  *kaydırma ifadesi*

*eşitlik ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik-ifade*  **==**  *ilişkisel ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik-ifade*  **! =**  *ilişkisel-ifade*

*Ve-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*AND ifadesi*  **&**  *eşitlik-ifadesi*

*dışlamalı OR ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*AND ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dışlamalı OR-ifadesi*  **^**  *ve-ifadesi*

*KAPSAMLı or-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dışlamalı OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*KAPSAMLı or ifadesi* **&#124;** *dışlamalı OR* ifadesi    

*MANTıKSAL and-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*kapsamlı OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal and ifadesi*  **&&**  *içinde or ifadesi*

*MANTıKSAL or ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal AND ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;mantıksal *or* -ifadesi **&#124;&#124;** *mantıksal and ifadesi*    

## <a name="see-also"></a>Ayrıca bkz.

- [Tümcecik Yapısı Dil Bilgisi](../c-language/phrase-structure-grammar.md)

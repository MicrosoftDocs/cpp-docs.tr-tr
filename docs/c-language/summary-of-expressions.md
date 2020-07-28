---
title: İfadelerin Özeti
ms.date: 06/14/2018
ms.assetid: ed448953-687a-4b57-a1cb-12967bd770ea
ms.openlocfilehash: 1660690c6d36aa1dbdc025d6afe92e19ff941463
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220840"
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
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **->** *tanımlayıcı*    <br/>
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
&nbsp;&nbsp;&nbsp;&nbsp;**`sizeof`**  *Birli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sizeof (**  *tür adı*  **)**

*birli-işleç*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**&****&#42;** **+** **-** **~** **!**

*Cast ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birli-ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(**  *tür adı*  **)**  *Cast ifadesi*

*çarpma ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Cast ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma* ifadesi **&#42;** *Cast ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma ifadesi* **/** *Cast ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma ifadesi* **%** *Cast ifadesi*    

*Toplamsal ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*çarpma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Toplamsal ifadesi* **+** *çarpma ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Toplamsal ifadesi* **-** *çarpma ifadesi*    

*SHIFT ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Toplamsal ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*SHIFT ifadesi*   * *SHIFT-Expression * eklenebilir-ifade \<\<**  *additive-expression*<br/> &nbsp; &nbsp; &nbsp; &nbsp; * **>>** *additive-expression*  

*ilişkisel ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*SHIFT ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-* * * \<**  *shift-expression*<br/> ifade &nbsp; &nbsp; ilişkisel &nbsp; -ifade * Shift-Expression ilikisel-Expression * * ilikisel-Expression * SHIFT-Expression &nbsp; * **>** *shift-expression* <br/> &nbsp; &nbsp; &nbsp; &nbsp;   ** \<=**  *shift-expression*<br/> &nbsp; &nbsp; &nbsp; &nbsp; * **>=** *shift-expression*    

*eşitlik ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik ifadesi* **==** *ilişkisel ifadesi*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik-ifade*  **! =**  *ilişkisel-ifade*

*Ve-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*And ifadesi* **&** *eşitlik ifadesi*    

*dışlamalı OR ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*AND ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dışlamalı OR ifadesi* **^** *And ifadesi*    

*KAPSAMLı or-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*dışlamalı OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*KAPSAMLı or ifadesi* **&#124;** *dışlamalı OR* ifadesi    

*MANTıKSAL and-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*kapsamlı OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MANTıKSAL and ifadesi* **&&** *KAPSAMLı or ifadesi*    

*MANTıKSAL or ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal AND ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;mantıksal *or* -ifadesi **&#124;&#124;** *mantıksal and ifadesi*    

## <a name="see-also"></a>Ayrıca bkz.

- [Tümcecik yapısı dil bilgisi](../c-language/phrase-structure-grammar.md)

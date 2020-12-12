---
description: 'Daha fazla bilgi edinin: C sabit Ifadeleri'
title: C Sabit İfadeleri
ms.date: 06/14/2018
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
ms.openlocfilehash: 82da5150b35035d96b28ff1091e754cb7043a5ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289523"
---
# <a name="c-constant-expressions"></a>C Sabit İfadeleri

Sabit bir ifade derleme zamanında değerlendirilir, çalışma süresi değildir ve bir sabit 'in kullanılabileceği herhangi bir yerde kullanılabilir. Sabit ifade, bu tür için gösterilebilir tablo değerleri aralığında olan bir sabit olarak değerlendirilmelidir. Sabit bir ifadenin işlenenleri tamsayı sabitler, karakter sabitleri, kayan nokta sabitleri, sabit listesi sabitleri, tür atamaları, **`sizeof`** ifadeler ve diğer sabit ifadeler olabilir.

## <a name="syntax"></a>Syntax

*sabit ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*

*koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MANTıKSAL or ifadesi* **?** *ifade* **:** *koşullu ifade*

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade* **,** *atama ifadesi*

*atama ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birli ifade* *atama-işleç* *atama-ifade*

*atama-işleç*: aşağıdakilerden biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**=****&#42;=** **/=** **%=** **+=** **-=** **\<\<=** **>>=** **&=** **^=** **&#124;=**

Struct Bildiricisi, Numaralandırıcı, doğrudan bildirimci, doğrudan soyut bildirimci ve etiketli deyim için terminalnonterminalleri, *sabit ifade* olmayan bir terminali içerir.

İntegral sabit ifadesi bir yapının bit alanı üyesinin boyutunu, sabit listesi sabitinin değerini, bir dizinin boyutunu veya bir sabitin değerini belirtmek için kullanılmalıdır **`case`** .

Önişlemci yönergelerinde kullanılan sabit ifadeler, ek kısıtlamalara tabidir. Sonuç olarak, bunlar "kısıtlı sabit ifadeler" olarak bilinir. Kısıtlı bir sabit ifade **`sizeof`** ifadeler, sabit listesi sabitleri, herhangi bir türe veya kayan tür sabitlerine tür atamaları içeremez. Ancak, tanımlı özel sabit ifade **(** _tanımlayıcı_ **)** içerebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [İşlenenler ve Ifadeler](../c-language/operands-and-expressions.md)

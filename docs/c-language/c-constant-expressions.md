---
title: C Sabit İfadeleri
ms.date: 06/14/2018
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
ms.openlocfilehash: f6984c47ef8acde462a8e92e01b72ef26a61eddc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325747"
---
# <a name="c-constant-expressions"></a>C Sabit İfadeleri

Sabit bir ifade derleme zamanında değerlendirilir, çalışma süresi değildir ve bir sabit 'in kullanılabileceği herhangi bir yerde kullanılabilir. Sabit ifade, bu tür için gösterilebilir tablo değerleri aralığında olan bir sabit olarak değerlendirilmelidir. Sabit bir ifadenin işlenenleri tamsayı sabitler, karakter sabitleri, kayan nokta sabitleri, sabit listesi sabitleri, tür atamaları, **sizeof** ifadeleri ve diğer sabit ifadeler olabilir.

## <a name="syntax"></a>Sözdizimi

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
&nbsp;&nbsp;&nbsp;&nbsp;**=****&#42;** **/=** **%=** = **+=** **-=** **&#124;** = ** \< \< ** **>>=** **&=** **^=**

Struct Bildiricisi, Numaralandırıcı, doğrudan bildirimci, doğrudan soyut bildirimci ve etiketli deyim için terminalnonterminalleri, *sabit ifade* olmayan bir terminali içerir.

Bir integral sabit ifadesi, bir yapının bit alanı üyesinin boyutunu, bir numaralandırma sabitinin değerini, bir dizinin boyutunu veya bir **Case** sabitinin değerini belirtmek için kullanılmalıdır.

Önişlemci yönergelerinde kullanılan sabit ifadeler, ek kısıtlamalara tabidir. Sonuç olarak, bunlar "kısıtlı sabit ifadeler" olarak bilinir. Kısıtlı bir sabit ifade, **sizeof** ifadeleri, Numaralandırma sabitleri, herhangi bir türe veya kayan tür sabitlerine tür atamaları içeremez. Ancak, tanımlı özel sabit ifade **(** _tanımlayıcı_ **)** içerebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [İşlenenler ve Ifadeler](../c-language/operands-and-expressions.md)

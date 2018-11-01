---
title: C Sabit İfadeleri
ms.date: 06/14/2018
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
ms.openlocfilehash: f6984c47ef8acde462a8e92e01b72ef26a61eddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490538"
---
# <a name="c-constant-expressions"></a>C Sabit İfadeleri

Sabit bir ifade, derleme zamanında çalışma zamanı, değil olarak değerlendirilir ve bir sabit kullanılabilir herhangi bir yerde kullanılabilir. Sabit ifade türü temsil edilebilir değerler aralığında olan bir sabit değerlendirilmelidir. İşlenen bir sabit ifade can'ın olması tamsayı sabitlerini, karakter sabitlerini, kayan nokta sabitleri, numaralandırma sabitlerini, atamalar yazın **sizeof** ifadeler ve diğer sabit ifadeler.

## <a name="syntax"></a>Sözdizimi

*Sabit ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*

*Koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-veya-ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-veya-expression* **?** *ifade* **:** *koşullu ifade*

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade* **,** *atama ifadesi*

*atama ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Koşullu ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tekli ifade* *atama işleci* *atama ifadesi*

*atama işleci*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**=** **&#42;=** **/=** **%=** **+=** **-=** **\< \<=** **>>=** **&=** **^=** **&#124;=**

Terminal dışı yapı bildirimci, numaralandırıcı, doğrudan bildirimci, doğrudan soyut bildirimci ve etiketli deyim içeren *sabit-ifade* bildirimlere.

İntegral sabit ifadesi bir bit alanı üyesi bir yapının, bir numaralandırma sabit değeri, bir dizinin boyutunu ya da değerini boyutunu belirtmek için kullanılması gereken bir **çalışması** sabit.

Ön İşlemci yönergelerinde kullanılan sabit ifadeler ek kısıtlamalar geçerlidir. "Kısıtlı sabit ifadeler." sonuç olarak, bilinen Kısıtlı bir sabit ifade içeremez **sizeof** ifadeleri, numaralandırma sabitlerini, tüm tür veya değişken türü sabitleri atamaların yazın. Ancak, özel sabit ifade içerebileceği **tanımlanan (** _tanımlayıcı_ **)**.

## <a name="see-also"></a>Ayrıca bkz.

- [İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)

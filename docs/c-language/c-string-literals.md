---
title: C Dize Değişmez Değerleri
ms.date: 08/31/2018
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
ms.openlocfilehash: bd8b49645e34224cbea7e801f197bfbcbc012915
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635632"
---
# <a name="c-string-literals"></a>C Dize Değişmez Değerleri

Bir "dize sabit değeri" kaynak karakter çift tırnak işaretleri içindeki karakter dizisidir (**""**). Dize değişmez değerleri kullanılan bir dizi temsil etmek için bu karakterleri, birlikte ele alındığında, null ile sonlandırılmış bir dize oluşturur. Her zaman geniş dize değişmez değerleri harfiyle koymalısınız **L**.

## <a name="syntax"></a>Sözdizimi

*dize sabit değeri*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**"** *s karakter dizisi*<sub>iyileştirilmiş</sub> **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L"** *s karakter dizisi*<sub>iyileştirilmiş</sub> **"**

*s karakter dizisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s char*

&nbsp;&nbsp;&nbsp;&nbsp;*s karakter dizisi* *s char*

*s char*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;herhangi bir üyesi kaynak karakter kümesi çift tırnak işareti dışında ("), ters eğik çizgi (\\), veya yeni satır karakteri<br/>

&nbsp;&nbsp;&nbsp;&nbsp;*kaçış sırası*

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, basit bir dize sabit değeri verilmiştir:

```C
char *amessage = "This is a string literal.";
```

Tüm çıkış kodları listelenir [kaçış dizileri](../c-language/escape-sequences.md) tablo dize değişmez değerleri geçerlidir. Bir dize sabit değerinde çift tırnak işareti temsil etmek için kaçış sırasını kullanın  **\\"**. Tek tırnak işareti (**'**) çıkış sırası olmadan temsil edilebilir. Ters eğik çizgi (**\\**) ikinci bir ters eğik çizgiyle gelmelidir (**\\\\**) bir dize içinde olduğunda görünür. Ters eğik çizgi bir satırın sonunda göründüğünde, her zaman bir satır devamlılığı karakteri yorumlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[C Öğeleri](../c-language/elements-of-c.md)

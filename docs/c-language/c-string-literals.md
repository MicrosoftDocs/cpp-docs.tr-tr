---
title: C Dize Değişmez Değerleri
ms.date: 08/31/2018
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
ms.openlocfilehash: 0df7126efe5a5b2caa3a4fee51465d0dbe892e89
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400580"
---
# <a name="c-string-literals"></a>C Dize Değişmez Değerleri

"Dize sabit değeri", kaynak karakter kümesindeki, çift tırnak işaretleri (**""**) içine alınmış bir karakter dizisidir. Dize sabit değerleri, birlikte alınan bir karakter dizisini göstermek için kullanılır, null ile sonlandırılmış bir dize oluşturur. Geniş dize sabit değerlerini her zaman **L**harfiyle önekle sağlamalısınız.

## <a name="syntax"></a>Sözdizimi

*dize sabit değeri*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**"** *s-char-Sequence*<sub>opt</sub> **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L "** *s-char-Sequence*<sub>opt</sub> **"**

*s-char-Sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s-char*

&nbsp;&nbsp;&nbsp;&nbsp;*s-Char-dizi* *s-char*

*s-char*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Çift tırnak işareti ("), ters eğik çizgi (\\) veya yeni satır karakteri dışında kaynak karakter kümesinin herhangi bir üyesi

&nbsp;&nbsp;&nbsp;&nbsp;*kaçış sırası*

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnekte basit bir dize sabit değeri verilmiştir:

```C
char *amessage = "This is a string literal.";
```

[Kaçış dizileri](../c-language/escape-sequences.md) tablosunda listelenen tüm kaçış kodları dize sabit değerlerinde geçerlidir. Bir dize sabit değerinde çift tırnak işareti göstermek için, kaçış sırasını ** \\kullanın "**. Tek tırnak işareti (**'**), kaçış sırası olmadan gösterilebilir. Ters eğik çizgi**\\**(), bir dize içinde göründüğünde ikinci bir**\\**ters eğik çizgi () ile birlikte gelmelidir. Bir çizginin sonunda ters eğik çizgi göründüğünde, her zaman bir satır devamlılık karakteri olarak yorumlanır.

## <a name="see-also"></a>Ayrıca bkz.

[C Öğeleri](../c-language/elements-of-c.md)

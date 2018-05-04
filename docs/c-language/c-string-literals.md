---
title: C dize değişmez değerleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 303ad83c5e366f32a99a501a58b168ef25adbb42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-string-literals"></a>C Dize Değişmez Değerleri
Kaynak karakter çift tırnak işaretleri içindeki kümesindeki bir karakter dizisi bir "dize" olan (**""**). Dize değişmez değerleri kullanılan bir dizi göstermek için hangi karakterleri, birlikte ele alındığında null sonlandırılmış bir dize oluşturur. Her zaman wide dize değişmez değerleri harfiyle önek gerekir **L**.  
  
## <a name="syntax"></a>Sözdizimi  
 *değişmez dize değeri*:  
 **"** *s karakter dizisi* kabul **"**  
  
 **L"** *s karakter dizisi* kabul **"**  
  
 *s karakter dizisi*:  
 *s-char*  
  
 *s karakter dizisi s-char*  
  
 *s-char*:  
 Kaynak karakteri, herhangi bir üye kümesi çift tırnak işareti dışında ("), eğik çizgi (\\), ya da yeni satır karakteri  
  
 *kaçış sırası*  
  
 Aşağıdaki örnek, basit bir dize sabit değeri verilmiştir:  
  
```  
char *amessage = "This is a string literal.";  
```  
  
 Tüm çıkış kodları listelenen [kaçış sıraları](../c-language/escape-sequences.md) tablo dize değişmez değerleri geçerlidir. Bir dize sabit değeri içinde çift tırnak işareti temsil etmek için kaçış sırası kullanmak  **\\"**. Tek tırnak işareti (**'**) bir kaçış sırası temsil edilebilir. Ters eğik çizgi (**\\**) ikinci ters bölü işareti gelmelidir (**\\\\**) dizesi içinde görüntülendiğinde. Bir satırın sonunda bir ters eğik çizgi görüntülendiğinde, her zaman bir satır devamlılığı karakteri olarak yorumlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Öğeleri](../c-language/elements-of-c.md)
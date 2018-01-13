---
title: "C dize değişmez değerleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b0be3ee70ef708441d20fdbbc14f25f5102d734a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-string-literals"></a>C Dize Değişmez Değerleri
Kaynak karakter çift tırnak işaretleri içindeki kümesindeki bir karakter dizisi bir "dize" olan (**""**). Dize değişmez değerleri kullanılan bir dizi göstermek için hangi karakterleri, birlikte ele alındığında null sonlandırılmış bir dize oluşturur. Her zaman wide dize değişmez değerleri harfiyle önek gerekir **L**.  
  
## <a name="syntax"></a>Sözdizimi  
 *değişmez dize değeri*:  
 **"** *s karakter dizisi* kabul**"**  
  
 **L"** *s karakter dizisi* kabul**"**  
  
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
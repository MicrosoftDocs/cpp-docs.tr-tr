---
title: Belirteçleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- tokens [C++]
- parsing, C++ tokens
- translation units
- white space, in C++ tokens
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba2e1a6cc36e4e5f2f785c1e5dff03c6fb5e392d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="tokens-c"></a>Belirteçleri (C++)
Bir belirteç C++ programının derleyicisi için anlamlı olan en küçük öğesidir. C++ ayrıştırıcısı şu tür belirteçleri tanır: Tanımlayıcılar, anahtar sözcükler, sabitler, işleçler, noktalayıcılar ve diğer ayıraçlar. Bu belirteçlerin akışı bir çeviri birimi oluşturur.  
  
 Belirteçleri genellikle ayrılır *boşluk*. Bir veya daha fazla boşluk olabilir:  
  
-   Boşluklar  
  
-   Yatay veya dikey sekmeler  
  
-   Yeni satırlar  
  
-   Form beslemeleri  
  
-   Açıklamalar  
  
 Ayrıştırıcının anahtar sözcükler, tanımlayıcılar, değişmez değerleri, işleçler ve noktalama işaretleri tanır. Belirli belirteç türleri hakkında daha fazla bilgi için bkz: [anahtar sözcükleri](../cpp/keywords-cpp.md), [tanımlayıcıları](../cpp/identifiers-cpp.md), [sayısal, Boole ve işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md), [dize ve karakter değişmez değerleri ](../cpp/string-and-character-literals-cpp.md), [Kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md), [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md), ve [noktalama işaretleri](../cpp/punctuators-cpp.md). Beyaz alan ayırmak için gerektiği şekilde belirteçleri dışında yoksayılır.  
  
 Önişlem belirteçleri önişlem aşamalarında derleyiciye geçirilen belirteç akışı oluşturmak için kullanılır. Önişlem belirteci kategoriler üstbilgi adları, tanımlayıcılar, önişlem numaraları, karakter değişmez değerleri, dize değişmez değerleri, önişlem işleçler ve noktalama işaretleri ve diğer kategorilerden birini eşleşmiyor tek boşluk olmayan karakterler bulunur. Karakter ve dize değişmez değerleri, kullanıcı tanımlı değişmez değerler olabilir. Belirteçleri ön işleme boşluk veya açıklamalar tarafından ayrılabilir.  
  
 Ayrıştırıcı, soldan sağa taramada girdi karakterlerini kullanarak olası en uzun belirteci oluşturarak, belirteçleri girdi akışından ayırır. Bu kod parçasını göz önünde bulundurun:  
  
```  
a = i+++j;  
```  
  
 Kodu yazan programcı bu iki deyimden birini amaçlamış olabilir:  
  
```  
a = i + (++j)  
  
a = (i++) + j  
```  
  
 Ayrıştırıcı girdi akışından olası en uzun belirteci oluşturduğundan, ikinci yorumu seçer ve `i++`, `+` ile `j` belirtecini yapar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)
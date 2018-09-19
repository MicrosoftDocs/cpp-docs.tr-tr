---
title: Veri türü tanımlayıcıları ve eşdeğerleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68444d5ac8944e3c6679fce6397226d48206037f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092732"
---
# <a name="data-type-specifiers-and-equivalents"></a>Veri Türü Tanımlayıcıları ve Eşdeğerleri

Bu kitap, genellikle uzun biçimler yerine aşağıdaki tabloda listelenen tür tanımlayıcılarının biçimlerini kullanır ve `char` türünün varsayılan olarak işaretli olduğunu varsayar. Bu nedenle, bu kitap boyunca `char` eşdeğerdir **signed char**.

### <a name="type-specifiers-and-equivalents"></a>Tür Tanımlayıcıları ve Eşdeğerleri

|Tür Tanımlayıcısı|Eşdeğerleri|
|--------------------|---------------------|
|**signed char**1|**char**|
|**İmzalı int**|**İmzalı**, **int**|
|**İmzalı short int**|**kısa**, **kısa imzalı**|
|**İmzalı Long int**|**uzun**, **signed long**|
|**İmzasız char**|—|
|**işaretsiz int**|**İşaretsiz**|
|**İmzasız short int**|**İmzasız short**|
|**İmzasız long int**|**İmzasız long**|
|**float**|—|
|**uzun çift**2|—|

1 yaptığınızda **char** türü varsayılan olarak işaretsiz (/J derleyici seçeneğini belirterek) kısaltamazsınız **signed char** olarak **char**.

2 32 bit ve 64-bit işletim sistemleri, Microsoft C derleyicisi eşler **uzun çift** türüne **çift**.

**Microsoft'a özgü**

Varsayılan değeri değiştirmek için /J derleyici seçeneğini belirtebilirsiniz **char** türünü işaretli'den işaretsiz'e. Bu seçenek etkin olduğunda **char** aynı anlamına gelir **imzasız char**, ve kullanmalısınız **imzalı** işaretli bir karakter değeri bildirmek için anahtar sözcüğü. Varsa bir **char** değeri bildirilirse, /J seçeneği bunu etkilemez ve değer genişletildiğinde işaret genişletilmiş bir **int** türü. **Char** türüne genişletildiğinde sıfır Genişletilmiş **int** türü.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Tür Tanımlayıcıları](../c-language/c-type-specifiers.md)
---
title: Veri Türü Tanımlayıcıları ve Eşdeğerleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 4003d9427c160b0e1c725cdc591190bd9777b3de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234936"
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

## <a name="see-also"></a>Ayrıca bkz.

[C Tür Tanımlayıcıları](../c-language/c-type-specifiers.md)

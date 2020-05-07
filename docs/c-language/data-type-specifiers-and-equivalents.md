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

Bu kitap, genellikle uzun biçimler yerine aşağıdaki tabloda listelenen tür tanımlayıcılarının biçimlerini kullanır ve `char` türünün varsayılan olarak işaretli olduğunu varsayar. Bu nedenle, bu kitabın tamamında `char` , **imzalanmış char**ile eşdeğerdir.

### <a name="type-specifiers-and-equivalents"></a>Tür Tanımlayıcıları ve Eşdeğerleri

|Tür Tanımlayıcısı|Eşdeğerleri|
|--------------------|---------------------|
|**imzalanan karakter**1|**char**|
|**imzalanan int**|**imzalanan**, **int**|
|**imzalanan kısa tamsayı**|**kısa**, **imzalanmış kısa**|
|**imzalanan long int**|**uzun**, **imzalanan uzun**|
|**unsigned char**|—|
|**unsigned int**|**işaretlenmemiş**|
|**işaretsiz kısa tamsayı**|**imzasız short**|
|**işaretsiz long int**|**imzasız long**|
|**float**|—|
|**uzun çift**2|—|

1 **char** türünü varsayılan olarak işaretsiz hale getirerek (/j derleyici seçeneğini belirterek), **imzalanmış char** 'ı **char**olarak kısaltabilirsiniz.

2 32-bit ve 64 bit işletim sistemlerinde, Microsoft C derleyicisi **Long Double** 'u **Double**türüne eşler.

**Microsoft'a Özgü**

Varsayılan **karakter** türünü imzalanmış iken işaretsiz olarak değiştirmek için/j derleyici seçeneğini belirtebilirsiniz. Bu seçenek etkin olduğunda, **char** **işaretsiz char**ile aynı anlamına gelir ve imzalı bir karakter değeri bildirmek için **imzalı** anahtar sözcüğünü kullanmanız gerekir. Bir **char** değeri açıkça imzalı olarak bildirilirse,/j seçeneği bunu etkilemez ve bir **int** türü iletildiklerinde olduğunda değer, işaret genişletilir. İletildiklerinde to **int** Type olduğunda **char** türü sıfır genişletilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Tür Tanımlayıcıları](../c-language/c-type-specifiers.md)

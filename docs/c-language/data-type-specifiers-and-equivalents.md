---
title: "Veri türü tanımlayıcıları ve eşdeğerleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 596e3fcf4dab3f88abc17cac4bc32471e63b4bbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-type-specifiers-and-equivalents"></a>Veri Türü Tanımlayıcıları ve Eşdeğerleri
Bu kitap, genellikle uzun biçimler yerine aşağıdaki tabloda listelenen tür tanımlayıcılarının biçimlerini kullanır ve `char` türünün varsayılan olarak işaretli olduğunu varsayar. Bu nedenle, bu kitap boyunca `char` eşdeğerdir **char imzalı**.  
  
### <a name="type-specifiers-and-equivalents"></a>Tür Tanımlayıcıları ve Eşdeğerleri  
  
|Tür Tanımlayıcısı|Eşdeğerleri|  
|--------------------|---------------------|  
|**İmzalı char**1|**char**|  
|**İmzalı int**|**İmzalı**, **int**|  
|**İmzalı short int**|**kısa**, **kısa imzalı**|  
|**İmzalı Long int**|**uzun**, **signed long**|  
|**İmzasız char**|—|  
|**İmzasız int**|**İmzasız**|  
|**İmzasız short int**|**İmzasız short**|  
|**İmzasız long int**|**İmzasız long**|  
|**float**|—|  
|**uzun çift**2|—|  
  
 1 yaptığınızda **char** türü imzasız varsayılan olarak (/J derleyici seçeneği belirterek), kısaltma olamaz **char imzalı** olarak **char**.  
  
 2 Microsoft C Derleyici, 32 bit ve 64-bit işletim sistemleri, eşlemeleri **uzun çift** yazmak için **çift**.  
  
 **Microsoft özel**  
  
 Varsayılan değeri değiştirmek için /J derleyici seçeneği belirtebilirsiniz **char** türünden imzalı çok imzasız. Bu seçenek etkin olduğunda **char** aynı anlamına gelir **imzasız char**, ve kullanmanız gerekir **imzalı** imzalı karakter değeri bildirmek için anahtar sözcüğü. Varsa bir **char** değeri açıkça bildirilen imzalı, /J seçeneği etkilemez ve devam olduğunda oturum genişletilmiş değerdir bir **int** türü. **Char** türü devam olduğunda sıfır Genişletilmiş **int** türü.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Tür Tanımlayıcıları](../c-language/c-type-specifiers.md)
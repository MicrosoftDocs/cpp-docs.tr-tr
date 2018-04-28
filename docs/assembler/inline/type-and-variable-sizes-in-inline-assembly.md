---
title: Tür ve değişken boyutları satır içi derlemede | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- length
- Type
dev_langs:
- C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3466158c507e618e701df5aed35db7e5814abe52
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Satır İçi Derlemede Tür ve Değişken Boyutları
**Microsoft özel**  
  
 **UZUNLUĞU**, **BOYUTU**, ve **türü** işleçleri satır içi derlemede sınırlı bir anlama sahip. İle tüm kullanılamaz `DUP` işleci (MASM yönergeleri veya işleçleri ile tanımlayamazsınız nedeniyle). Ancak C veya C++ değişkenleri veya türleri boyutunu bulmak için kullanabilirsiniz:  
  
-   **UZUNLUĞU** işleci bir dizide öğe sayısını dönebilirsiniz. Dizi olmayan değişkenleri için 1 değerini döndürür.  
  
-   **BOYUTU** işleci C veya C++ değişkeni boyutunu dönebilirsiniz. Bir değişkenin boyutu ürünüdür kendi **UZUNLUĞU** ve **türü**.  
  
-   **Türü** işleci C veya C++ türü veya değişken boyutu dönebilirsiniz. Değişken bir dizi ise **türü** dizinin tek bir öğe boyutunu döndürür.  
  
 Örneğin, programınızın 8 öğe varsa `int` diziye  
  
```  
int arr[8];  
```  
  
 Aşağıdaki C ve derleme ifadeler boyutunu verim `arr` ve öğeleri.  
  
|__asm|C|Boyut|  
|-------------|-------|----------|  
|**Uzunluk** arr|`sizeof`(arr) /`sizeof`(arr[0])|8|  
|**BOYUTU** arr|`sizeof`(arr)|32|  
|**TÜR** arr|`sizeof`(arr[0])|4|  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)
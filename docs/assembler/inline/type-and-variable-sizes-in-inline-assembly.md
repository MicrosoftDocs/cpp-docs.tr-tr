---
title: "Tür ve değişken boyutları satır içi derlemede | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- length
- Type
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9edf9430c0333317a767e8f8c114453a6d80f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
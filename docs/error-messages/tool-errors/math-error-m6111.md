---
title: Matematik hatası M6111 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b03937ed442b169b960d573b44c0eb6ebca9660
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318002"
---
# <a name="math-error-m6111"></a>Matematik Hatası M6111
Yığında  
  
 Kayan nokta işlemi yığın underflow 287/8087/387 eşişlemcisi veya öykünücü ile sonuçlandı.  
  
 Bu hata genellikle bir çağrı tarafından neden bir `long double` bir değer döndürmüyor işlevi. Örneğin, aşağıdaki bu hata derlenmiş ve çalışma oluşturur:  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 Program 139 çıkış koduyla sona erer.
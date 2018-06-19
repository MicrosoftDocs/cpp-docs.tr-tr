---
title: Derleyici Hatası C2891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01741d1cc67f0045c46ab392212625b9e1a2d8ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246376"
---
# <a name="compiler-error-c2891"></a>Derleyici Hatası C2891
'parametresi': bir şablon parametresini adresi alınamıyor  
  
 Bir lvalue olmadığı sürece bir şablon parametresini adresini alamıyor. Tür parametreleri herhangi bir adres sahip oldukları için lvalues değildir. Lvalues olmayan şablon parametresi listelerinde olmayan tür değerleri de bir adresi yok. Şablon parametresi olarak geçirilen değer şablon bağımsız değişken derleyici tarafından üretilen bir kopyası olduğundan bu derleyici hatası C2891 neden olan kod örneğidir.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 Başvuru türleri gibi lvalues olan şablon parametreleri kendi adres gerçekleştirmişsiniz.  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 Bu hatayı düzeltmek için bir lvalue olmadığı sürece bir şablon parametresini adresini kazanmaz.
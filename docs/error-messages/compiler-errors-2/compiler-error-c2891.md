---
title: "Derleyici Hatası C2891 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 979d77ad5b5bd0b68dd539695d6cb1b60b099c55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
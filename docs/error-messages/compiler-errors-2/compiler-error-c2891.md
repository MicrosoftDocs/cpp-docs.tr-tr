---
title: "Derleyici Hatası C2891 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2891
dev_langs: C++
helpviewer_keywords: C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6c35294472fe4142e7e6689adfc5f5f71c27b664
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
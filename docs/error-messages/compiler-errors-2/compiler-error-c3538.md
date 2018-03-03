---
title: "Derleyici Hatası C3538 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3538
dev_langs:
- C++
helpviewer_keywords:
- C3538
ms.assetid: ef3698a5-7356-4c62-b9af-5d3a4baed958
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 111e75b562020057596baf3f778d97cdab2ab528
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3538"></a>Derleyici Hatası C3538
bildirimcisi listesinde 'auto' her zaman aynı türünü türetme gerekir  
  
 Aynı türde bir bildirim listesinde bildirilen tüm değişkenleri çözümleme.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Emin tüm `auto` bildirimler listesinde aynı türünü türetme.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki deyimleri C3538 verim. Her deyimi her kullanımını ancak birden çok değişkenler bildirilmektedir `auto` anahtar sözcüğü aynı türünü türetme değil.  
  
```  
// C3538.cpp  
// Compile with /Zc:auto  
// C3538 expected  
int main()  
{  
// Variable x1 is a pointer to char, but y1 is a double.  
   auto * x1 = "a", y1 = 3.14;    
// Variable c is a char and c1 is char*, but c2, and c3 are pointers to pointers.  
   auto c = 'a', *c1 = &c, * c2 = &c1, * c3 = &c2;   
// Variable x2 is an int, but y2 is a double and z is a char.  
   auto x2(1), y2(0.0), z = 'a';   
// Variable a is a pointer to int, but b is a pointer to double.  
   auto *a = new auto(1), *b = new auto(2.0);   
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
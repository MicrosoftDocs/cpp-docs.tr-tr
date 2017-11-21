---
title: false (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: false_cpp
dev_langs: C++
helpviewer_keywords: false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 47052993f9bfc003310da8c0ead47f62dddcc298
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="false-c"></a>false (C++)
Anahtar sözcüğü türünde bir değişken için iki değerlerinden biri [bool](../cpp/bool-cpp.md) veya koşullu ifade (koşullu ifade sunulmuştur bir **true** Boole ifadesi). Örneğin, varsa `i` bir değişken türü `bool`, `i = false;` deyimi atar **false** için `i`.  
  
## <a name="example"></a>Örnek  
  
```  
// bool_false.cpp  
#include <stdio.h>  
  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
```Output  
1  
0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)
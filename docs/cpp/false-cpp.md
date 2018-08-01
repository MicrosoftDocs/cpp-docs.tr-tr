---
title: false (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- false_cpp
dev_langs:
- C++
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b45db3a1226a9069c03ff928227a8719c83eb65
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406526"
---
# <a name="false-c"></a>false (C++)
Anahtar sözcüğü bir değişken türü için iki değerlerden biri [bool](../cpp/bool-cpp.md) ya da bir koşullu ifade (artık bir koşullu ifade olan bir **true** Boole ifadesi). Örneğin, varsa `i` türünde bir değişken **bool**, `i = false;` deyimi atar **false** için `i`.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)
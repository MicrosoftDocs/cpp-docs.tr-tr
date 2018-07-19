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
ms.openlocfilehash: a743398b60bc51118045b00e8caf4effde2c68da
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948027"
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)
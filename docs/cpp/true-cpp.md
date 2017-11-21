---
title: TRUE (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: true_cpp
dev_langs: C++
helpviewer_keywords: true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a5d0918d1236f28611c4dd57ee292659eb8f0fce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="true-c"></a>true (C++)
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar sözcük türünde bir değişken için iki değerlerinden biri [bool](../cpp/bool-cpp.md) veya (koşullu ifade şimdi bir ifadedir true boolean) koşullu bir ifade. Varsa `i` türü `bool`, ardından deyimi `i = true;` atar **true** için `i`.  
  
## <a name="example"></a>Örnek  
  
```  
// bool_true.cpp  
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
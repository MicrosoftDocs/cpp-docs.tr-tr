---
title: "Nasıl yapılır: eşitlik için Test yapma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: equality, testing for
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cbaddee30c9b02b99c10852b7e9c0d425d80ebb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-test-for-equality-ccli"></a>Nasıl yapılır: Eşitlik için Test Yapma (C++/CLI)
Aşağıdaki örnekte, ne işleyicilerin başvurduğu bir eşitlik için test C++ için Yönetilen Uzantılar kullanan temel alır.  
  
## <a name="example"></a>Örnek  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 Bu program için IL dönüş değeri op_Equality çağrısı kullanarak uygulandığını gösterir.  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CLI)](../dotnet/managed-types-cpp-cli.md)
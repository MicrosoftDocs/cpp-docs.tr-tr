---
title: alignof ve alignas (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a506a3c44c3304e786c41a2eb049939d317778e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="alignof-and-alignas-c"></a>alignof ve alignas (C++)
`alignas` Tür belirteci değişkenler ve kullanıcı tanımlı türler özel hizalamasını belirtmek için bir yoldur taşınabilir, C++ standart. `alignof` İşlecidir benzer şekilde belirtilen türe veya değişken hizalamasını elde etmek için standart ve taşınabilir bir yol.  
  
## <a name="example"></a>Örnek  
 Kullanabileceğiniz `alignas` harfi veya birleşim, bir sınıf ya da tek tek üyeleri. Zaman birden çok `alignas` tanımlayıcıları ile karşılaşıldı, derleyici (en büyük değere sahip bir) sıkı bir seçeceksiniz.  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizalama](../cpp/alignment-cpp-declarations.md)
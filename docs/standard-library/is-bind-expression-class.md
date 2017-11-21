---
title: "is_bind_expression sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: functional/std::is_bind_expression
dev_langs: C++
helpviewer_keywords: is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f8a21e0f59be12286fa10f5fe862f01eb3cef216
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isbindexpression-class"></a>is_bind_expression Sınıfı
Türü çağırarak oluşturursa testleri `bind`.  
  
## <a name="syntax"></a>Sözdizimi  
  
şablonu<class Ty>  
Yapı is_bind_expression {  
   statik const bool değeri;  
   };  
  
## <a name="remarks"></a>Açıklamalar  
Sabit üye `value` true ise türü `Ty` yapılan bir çağrı tarafından döndürülen bir türü `bind`, aksi takdirde false.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__functional__is_bind_expression.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}  
```  
  
```Output  
0  
1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [bağlama](../standard-library/functional-functions.md#bind)


---
title: "is_placeholder sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: functional/std::is_placeholder
dev_langs: C++
helpviewer_keywords: is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ceccd17b424630c225bd7de6781fd19f8f44bc7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isplaceholder-class"></a>is_placeholder Sınıfı
Test türü bir yer tutucudur.  
  
## <a name="syntax"></a>Sözdizimi  
  
Yapı is_placeholder {  
   statik const Int değeri;  
   };  
  
## <a name="remarks"></a>Açıklamalar  
 Sabit değer `value` 0 ise türü `Ty` bir yer tutucu; değil Aksi takdirde değerini bağlandığı işlev çağrısı bağımsız değişkeni konumudur. Değeri belirlemek için kullandığınız `N` n. yer tutucunun `_N`.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__functional__is_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
using namespace std::placeholders;   
  
template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}  
```  
  
```Output  
0  
3  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_1 nesnesi](../standard-library/1-object.md)


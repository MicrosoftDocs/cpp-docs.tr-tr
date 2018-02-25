---
title: "aligned_union sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::aligned_union
dev_langs:
- C++
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10f729463bca1325617831c3d558048416e105e2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="alignedunion-class"></a>aligned_union Sınıfı
Bir birleşim türü ve gerekli boyutu depolamak için bir POD türü büyüklükte ve uygun hizalanmış sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <std::size_t Len, class... Types>  
struct aligned_union;  
 
template <std::size_t Len, class... Types>  
using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Len`  
 Birleşim en büyük türünde hizalama değeri.  
  
 `Types`  
 Temel alınan UNION farklı türler.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı UNION başlatılmamış deposunda depolamak için gereken boyutu ve hizalama almak için kullanın. Üye typedef `type` bir POD adlarını yazın listelenen herhangi bir türde depolama için uygun `Types`; minimum boyutu `Len`. Statik üye `alignment_value` türü `std::size_t` listelenen her türlü gerekli sıkı hizalama içeren `Types`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `aligned_union` UNION yerleştirmek için bir hizalanmış yığını arabelleği ayrılamadı.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
value of u->i is 1065353216  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)   
 [alignment_of Sınıfı](../standard-library/alignment-of-class.md)

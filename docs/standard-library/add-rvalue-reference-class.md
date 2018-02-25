---
title: "add_rvalue_reference sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a42d8807763651f92ad87120fb50990821d03649
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference Sınıfı
Bir şablon parametresi rvalue başvuru türünde bir nesne veya işlev türü ise oluşturur. Aksi takdirde, daraltma başvuru semantiği nedeniyle, şablon parametresi ile aynı türüdür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```  
  
#### <a name="parameters"></a>Parametreler  
 T  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 `add_rvalue_reference` Sınıf adında bir üyeye sahip `type`, şablon parametresi için bir rvalue başvuru türü için bir diğer ad olduğu `T`. Daraltma başvuru semantiği, nesne olmayan ve işlev olmayan türleri için kapsıyor `T`, `T&&` olan bir `T`. Örneğin, `T` bir lvalue başvuru türü `add_rvalue_reference<T>::type` lvalue başvuru rvalue başvuru türüdür.  
  
 Kolaylık sağlamak için < type_traits > tanımlayan bir yardımcı şablonu `add_rvalue_reference_t`, bu diğer adları `type` üyesi `add_rvalue_reference`.  
  
## <a name="example"></a>Örnek  
 Bu kod örneği, nasıl rvalue başvuru türleri kullanılarak oluşturulan göstermek için static_assert kullanır. `add_rvalue_reference` ve `add_rvalue_reference_t`ve nasıl sonucu `add_rvalue_reference` lvalue başvuru türü rvalue başvuru değil, ancak lvalue başvuru türüne daraltır.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: < type_traits > Namespace: std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_lvalue_reference sınıfı](../standard-library/add-lvalue-reference-class.md)   
 [is_rvalue_reference Sınıfı](../standard-library/is-rvalue-reference-class.md)

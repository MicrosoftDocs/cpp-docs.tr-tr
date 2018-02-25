---
title: "reference_wrapper sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
dev_langs:
- C++
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0751f1fde7d49d11ecaab5628ac02f322628b5c8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="referencewrapper-class"></a>reference_wrapper Sınıfı
Bir başvuru sarmalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty>  
class reference_wrapper  
{  
public:  
    typedef Ty type;  
 
    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types> 
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
 
private:  
    Ty *ptr; // exposition only  
};  
```  
  
## <a name="remarks"></a>Açıklamalar  
A `reference_wrapper<Ty>` bir kopya oluşturulabilir ve bir nesne ya da bir işlev türü başvuru geçici kopya atanabilir sarmalayıcı `Ty`, bu tür bir nesneye işaret eden bir işaretçi sahiptir. A `reference_wrapper` başvuru tarafından standart kapsayıcılarında başvurularını depolamak ve nesneleri geçirmek için kullanılabilir `std::bind`.  
  
Tür `Ty` bir nesne türü veya bir işlev türü ya da derleme zamanında statik assert başarısız olması gerekir.  
  
Yardımcı işlevleri [std::ref](functional-functions.md#ref) ve [std::cref](functional-functions.md#cref) oluşturmak için kullanılan `reference_wrapper` nesneleri.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[reference_wrapper](#reference_wrapper)|Oluşturan bir `reference_wrapper`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[result_type](#result_type)|Sarmalanan başvuru zayıf sonuç türü.|  
|[Türü](#type)|Sarmalanan başvuru türü.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[get](#get)|Sarmalanan başvuru edinir.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[reference_wrapper::operator Ty&amp;](#op_ty_amp)|Bir işaretçi Sarmalanan başvuruyu alır.|  
|[reference_wrapper::operator()](#op_call)|Sarmalanan başvuru çağırır.|  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<işlevsel >  
  
 **Namespace:** std  
  
##  <a name="get"></a>  reference_wrapper::get  
 Sarmalanan başvuru edinir.  
  
```  
Ty& get() const noexcept;
```  
  
### <a name="remarks"></a>Açıklamalar  
Üye işlevini Sarmalanan başvuru döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__functional__reference_wrapper_get.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="op_ty_amp">reference_wrapper::operator Ty</a>&amp;  
 Sarmalanan referansını alır.  
  
```  
operator Ty&() const noexcept;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci döndürür `*ptr`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__functional__reference_wrapper_operator_cast.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "(int)rwi = " << (int)rwi << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
(int)rwi = 1  
```  
  
##  <a name="op_call"></a>  reference_wrapper::operator()  
 Sarmalanan başvuru çağırır.  
  
```  
template <class... Types>  
auto operator()(Types&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
 `Types`  
 Bağımsız değişken listesi türleri.  
  
 `args`  
 Bağımsız değişken listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon üye `operator()` döndürür `std::invoke(get(), std::forward<Types>(args)...)`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__functional__reference_wrapper_operator_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    std::reference_wrapper<int (int)> rwi(neg);   
  
    std::cout << "rwi(3) = " << rwi(3) << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
rwi(3) = -3  
```  
  
##  <a name="reference_wrapper"></a>  reference_wrapper::reference_wrapper  
 Oluşturan bir `reference_wrapper`.  
  
```  
reference_wrapper(Ty& val) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Ty`  
 Kaydırma türü.  
  
 `val`  
 Sarım değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Depolanan değer Oluşturucusu ayarlar `ptr` için `&val`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__functional__reference_wrapper_reference_wrapper.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="result_type"></a>  reference_wrapper::result_type  
 Sarmalanan başvuru zayıf sonuç türü.  
  
```  
typedef R result_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `result_type` Typedef olan bir eş anlamlı sarmalanmış işlev zayıf sonuç türü için. Bu typedef yalnızca işlev türleri için anlamlıdır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__functional__reference_wrapper_result_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    typedef std::reference_wrapper<int (int)> Mywrapper;   
    Mywrapper rwi(neg);   
    Mywrapper::result_type val = rwi(3);   
  
    std::cout << "val = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
val = -3  
```  
  
##  <a name="type"></a>  reference_wrapper::type  
 Sarmalanan başvuru türü.  
  
```  
typedef Ty type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon bağımsız değişken eşanlamlısı typedef olduğu `Ty`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__functional__reference_wrapper_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    typedef std::reference_wrapper<int> Mywrapper;   
    Mywrapper rwi(i);   
    Mywrapper::type val = rwi.get();   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [cref](../standard-library/functional-functions.md#cref)   
 [ref](../standard-library/functional-functions.md#ref)


---
title: reference_wrapper Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
ms.openlocfilehash: 623e1480bdec85120e504c8dc71b28d017c8872a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845074"
---
# <a name="reference_wrapper-class"></a>reference_wrapper Sınıfı

Bir başvuruyu sarmalanmış.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
class reference_wrapper
{
    typedef Ty type;

    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types>
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
};
```

## <a name="remarks"></a>Açıklamalar

, Bir `reference_wrapper<Ty>` kopya oluşturulabilir ve bir nesne ya da türü bir işlev başvurusu etrafında atanabilir sarmalayıcı kopyalayabilir ve `Ty` Bu türün bir nesnesine işaret eden bir işaretçi tutar. Bir `reference_wrapper` , başvuruları standart kapsayıcılarda depolamak ve başvuruya göre nesneleri geçirmek için kullanılabilir `std::bind` .

Tür, `Ty` bir nesne türü veya işlev türü olmalıdır ya da derleme zamanında statik bir onaylama başarısız olur.

[Std:: ref](functional-functions.md#ref) ve [std:: cref](functional-functions.md#cref) yardımcı işlevleri nesne oluşturmak için kullanılabilir `reference_wrapper` .

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[reference_wrapper](#reference_wrapper)|Bir oluşturur `reference_wrapper` .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[result_type](#result_type)|Sarmalanmış başvurunun zayıf sonuç türü.|
|[türüyle](#type)|Sarmalanan başvurunun türü.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[Al](#get)|Sarmalanan başvuruyu edinir.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç Ty&amp;](#op_ty_amp)|Kaydırılan başvuruya yönelik bir işaretçi alır.|
|[operator ()](#op_call)|Sarmalanan başvuruyu çağırır.|

## <a name="get"></a><a name="get"></a> Al

Sarmalanan başvuruyu edinir.

```cpp
Ty& get() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi Sarmalanan başvuruyu döndürür.

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

## <a name="operator-tyamp"></a><a name="op_ty_amp"></a> işleç Ty&amp;

Sarmalanan başvuruyu alır.

```cpp
operator Ty&() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `*ptr` .

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

## <a name="operator"></a><a name="op_call"></a> operator ()

Sarmalanan başvuruyu çağırır.

```cpp
template <class... Types>
auto operator()(Types&&... args);
```

### <a name="parameters"></a>Parametreler

*Türü*\
Bağımsız değişken liste türleri.

*args*\
Bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

Şablon üyesi `operator()` döndürür `std::invoke(get(), std::forward<Types>(args)...)` .

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

## <a name="reference_wrapper"></a><a name="reference_wrapper"></a> reference_wrapper

Bir oluşturur `reference_wrapper` .

```cpp
reference_wrapper(Ty& val) noexcept;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sarılacağı tür.

*Acil*\
Sarılacağı değer.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, saklı değerini olarak ayarlar `ptr` `&val` .

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

## <a name="result_type"></a><a name="result_type"></a> result_type

Sarmalanmış başvurunun zayıf sonuç türü.

```cpp
typedef R result_type;
```

### <a name="remarks"></a>Açıklamalar

`result_type`Typedef, Sarmalanan bir işlevin zayıf sonuç türü için bir eş anladır. Bu typedef yalnızca işlev türleri için anlamlıdır.

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

## <a name="type"></a><a name="type"></a> türüyle

Sarmalanan başvurunun türü.

```cpp
typedef Ty type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, şablon bağımsız değişkeninin eşanlamlısıdır `Ty` .

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

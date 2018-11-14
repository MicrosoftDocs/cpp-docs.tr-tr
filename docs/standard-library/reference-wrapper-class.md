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
ms.openlocfilehash: baf38dd637e31f6fabdf869a242f8f18e2812717
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525242"
---
# <a name="referencewrapper-class"></a>reference_wrapper Sınıfı

Bir başvuru sarmalar.

## <a name="syntax"></a>Sözdizimi

```cpp
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

A `reference_wrapper<Ty>` atmamalıdır kopyalama ve kopyalama atanabilir sarmalayıcı geçici bir nesne veya bir işlev türü başvuru `Ty`ve bu türdeki bir nesneye işaret eden bir işaretçi tutar. A `reference_wrapper` depolama başvurularının standart kapsayıcıları ve nesneleri geçirmek için başvuru tarafından kullanılabilir `std::bind`.

Türü `Ty` bir nesne türü veya bir işlev türü veya derleme zamanında bir statik onay başarısız olması gerekir.

Yardımcı işlevleri [std::ref](functional-functions.md#ref) ve [std::cref](functional-functions.md#cref) oluşturmak için kullanılan `reference_wrapper` nesneleri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[reference_wrapper](#reference_wrapper)|Oluşturur bir `reference_wrapper`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[result_type](#result_type)|Sarmalanan başvuru zayıf sonuç türü.|
|[Türü](#type)|Sarmalanan bir başvuru türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[get](#get)|Sarmalanan bir başvuru edinir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[reference_wrapper::operator Ty&amp;](#op_ty_amp)|Sarmalanan başvurusu bir işaretçi alır.|
|[reference_wrapper::operator()](#op_call)|Sarmalanan başvuru çağırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="get"></a>  reference_wrapper::get

Sarmalanan bir başvuru edinir.

```cpp
Ty& get() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sarmalanmış bir başvuru döndürür.

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

## <a name="op_ty_amp"></a>  reference_wrapper::operator Ty&amp;

Sarmalanan referansını alır.

```cpp
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

## <a name="op_call"></a>  reference_wrapper::operator()

Sarmalanan başvuru çağırır.

```cpp
template <class... Types>
auto operator()(Types&&... args);
```

### <a name="parameters"></a>Parametreler

*Türler*<br/>
Bağımsız değişken listesi türleri.

*bağımsız değişken*<br/>
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

## <a name="reference_wrapper"></a>  reference_wrapper::reference_wrapper

Oluşturur bir `reference_wrapper`.

```cpp
reference_wrapper(Ty& val) noexcept;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Kaydırmak için türü.

*VAL*<br/>
Sarım değeri.

### <a name="remarks"></a>Açıklamalar

Oluşturucu depolanan değeri ayarlar `ptr` için `&val`.

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

## <a name="result_type"></a>  reference_wrapper::result_type

Sarmalanan başvuru zayıf sonuç türü.

```cpp
typedef R result_type;
```

### <a name="remarks"></a>Açıklamalar

`result_type` Typedef olan Sarmalanan işlevinin zayıf sonucu türe ilişkin bir eşanlam. Bu tür tanımı, yalnızca işlev türleri için anlamlıdır.

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

## <a name="type"></a>  reference_wrapper::type

Sarmalanan bir başvuru türü.

```cpp
typedef Ty type;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon bağımsız değişkeni eşanlamlıdır `Ty`.

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

## <a name="see-also"></a>Ayrıca bkz.

[cref](../standard-library/functional-functions.md#cref)<br/>
[ref](../standard-library/functional-functions.md#ref)<br/>

---
description: 'Hakkında daha fazla bilgi edinin: is_pod sınıfı'
title: is_pod Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_pod
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
ms.openlocfilehash: b5fd263a0f17831daf7a187c4f0f32a5a635a9d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323557"
---
# <a name="is_pod-class"></a>is_pod Sınıfı

Tür POD ise sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_pod;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

`is_pod<T>::value`**`true`** *T* türü düz eskı veriler (pod) ise. Aksi takdirde, **`false`** .

Aritmetik türler, numaralandırma türleri, işaretçi türleri ve üye türleri işaretçisi POD.

POD türünün CV nitelikli bir sürümü bir POD türüdür.

POD 'un bir dizisi kendi POD olur.

Tüm statik olmayan veri üyeleri POD olan bir yapı veya birleşim, varsa, kendi POD olan bir yapıdır:

- Kullanıcı tarafından bildirilmeyen Oluşturucu yok.

- Özel veya korumalı statik olmayan veri üyesi yok.

- Temel olmayan sınıflar.

- Sanal işlev yok.

- Başvuru türündeki statik olmayan veri üyesi yok.

- Kullanıcı tanımlı kopya atama işleci yok.

- Kullanıcı tanımlı yıkıcı yok.

Bu nedenle, POD yapılar ve diziler içeren POD yapılarını ve dizilerini yinelemeli olarak oluşturabilirsiniz.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_pod.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial {
    int val;
};

struct throws {
    throws() {}  // User-declared ctor, so not POD

    int val;
};

int main() {
    std::cout << "is_pod<trivial> == " << std::boolalpha
        << std::is_pod<trivial>::value << std::endl;
    std::cout << "is_pod<int> == " << std::boolalpha
        << std::is_pod<int>::value << std::endl;
    std::cout << "is_pod<throws> == " << std::boolalpha
        << std::is_pod<throws>::value << std::endl;

    return (0);
}
```

```Output
is_pod<trivial> == true
is_pod<int> == true
is_pod<throws> == false
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)

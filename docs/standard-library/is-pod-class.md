---
title: is_pod sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c655ea4adec0364f35d0b43c637eae9c270cdb0e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962071"
---
# <a name="ispod-class"></a>is_pod Sınıfı

POD türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_pod;
```

### <a name="parameters"></a>Parametreler

*T* Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

`is_pod<T>::value` olan **true** , türü *T* olan düz eski veri (POD). Aksi halde kalır **false**.

Aritmetik tür, sabit listesi türleri, işaretçi türleri ve işaretçi üye türleri için POD ' dir.

Bir POD türü cv tam bir sürümünü kendisi bir POD türüdür.

POD kendisini POD dizisidir.

Varsa bir yapıda veya birleşimde, statik olmayan veri üyeleri POD tümü, kendisini POD verilmiştir:

- Kullanıcı bildirimi Oluşturucusu.

- Özel veya korumalı statik olmayan veri üye yok.

- Temel olmayan sınıflar.

- Sanal işlev yok.

- Başvuru türü statik olmayan veri üye yok.

- Hiçbir kullanıcı tanımlı kopya atama işleci.

- Hiçbir kullanıcı tarafından tanımlanan yıkıcı.

Bu nedenle, yinelemeli olarak derleme POD yapıları ve POD yapıları ve dizileri içeren dizileri kullanabilirsiniz.

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

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>

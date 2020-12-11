---
description: 'Hakkında daha fazla bilgi edinin: remove_pointer sınıfı'
title: remove_pointer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_pointer
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
ms.openlocfilehash: 8739fcd197dc59f5163740d1290abd3faee1922a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159667"
---
# <a name="remove_pointer-class"></a>remove_pointer Sınıfı

Türü işaretçiden türe ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_pointer;

template <class T>
using remove_pointer_t = typename remove_pointer<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Bir örneği, `remove_pointer<T>` `T1` *t* `T1*` ,, veya, `T1* const` `T1* volatile` `T1* const volatile` değilse *t* biçiminde olan bir değiştirilmiş türü tutar.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_pointer_t<int *> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_pointer_t<int *> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_pointer_t<int *> == int
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)\
[add_pointer sınıfı](../standard-library/add-pointer-class.md)

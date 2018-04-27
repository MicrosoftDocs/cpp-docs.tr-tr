---
title: is_default_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_default_constructible
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50f263e7621d3a53e3dac8e04a4fd74a02af3b6a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isdefaultconstructible-class"></a>is_default_constructible sınıfı

Bir türü varsayılan bir oluşturucu varsa testleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` false tuttuğu varsayılan bir oluşturucu, aksi takdirde sahip bir sınıf türü. Bu koşulu eşdeğerdir `is_constructible<T>`. Tür `T` tam bir tür olmalıdır `void`, veya bilinmeyen bağlı bir dizi.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>

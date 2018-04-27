---
title: is_signed sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_signed
dev_langs:
- C++
helpviewer_keywords:
- is_signed class
- is_signed
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8791270e6a61e75f5cba49c23f88ce654b07462a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="issigned-class"></a>is_signed Sınıfı

İmzalı tamsayı türü ise, test edin.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_signed;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Ty` imzalı tam sayı türü veya `cv-qualified` false tuttuğu tam sayı, aksi takdirde türdür.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_signed.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_signed<trivial> == " << std::boolalpha
        << std::is_signed<trivial>::value << std::endl;
    std::cout << "is_signed<int> == " << std::boolalpha
        << std::is_signed<int>::value << std::endl;
    std::cout << "is_signed<unsigned int> == " << std::boolalpha
        << std::is_signed<unsigned int>::value << std::endl;
    std::cout << "is_signed<float> == " << std::boolalpha
        << std::is_signed<float>::value << std::endl;

    return (0);
    }

```

```Output
is_signed<trivial> == false
is_signed<int> == true
is_signed<unsigned int> == false
is_signed<float> == false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_unsigned Sınıfı](../standard-library/is-unsigned-class.md)<br/>

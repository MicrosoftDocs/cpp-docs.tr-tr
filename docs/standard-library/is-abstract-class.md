---
title: is_abstract sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_abstract
dev_langs:
- C++
helpviewer_keywords:
- is_abstract class
- is_abstract
ms.assetid: 8867f660-3434-404c-ba90-c26607a5e0d2
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd63a308d274b6cfe83c2a22ba9859d6570497a1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isabstract-class"></a>is_abstract Sınıfı

Tür ise testleri soyut sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_abstract;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu en az bir saf sanal işlev, aksi takdirde sahip bir sınıftır.

## <a name="example"></a>Örnek

```cpp
// std__type_traits__is_abstract.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct abstract
    {
    virtual int val() = 0;
    };

int main()
    {
    std::cout << "is_abstract<trivial> == " << std::boolalpha
        << std::is_abstract<trivial>::value << std::endl;
    std::cout << "is_abstract<abstract> == " << std::boolalpha
        << std::is_abstract<abstract>::value << std::endl;

    return (0);
    }
```

```Output
is_abstract<trivial> == false
is_abstract<abstract> == true
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_polymorphic Sınıfı](../standard-library/is-polymorphic-class.md)<br/>

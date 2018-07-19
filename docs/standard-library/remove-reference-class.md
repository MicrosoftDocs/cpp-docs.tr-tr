---
title: remove_reference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_reference
dev_langs:
- C++
helpviewer_keywords:
- remove_reference class
- remove_reference
ms.assetid: 294e1965-3ae3-46ee-bc42-4fdf60c24717
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 343acc8d23e2b67c1e9f7556ffe2268c94bb3c63
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957908"
---
# <a name="removereference-class"></a>remove_reference Sınıfı

Türden başvuru türü yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_reference;

template <class T>
using remove_reference_t = typename remove_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

*T* değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Örneği `remove_reference<T>` bir değişiklik-tür tutar `T1` olduğunda *T* biçimindedir `T1&`, aksi takdirde *T*.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_reference_t<int&> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_reference_t<int&> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_reference_t<int&> == int
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_lvalue_reference Sınıfı](../standard-library/add-lvalue-reference-class.md)<br/>

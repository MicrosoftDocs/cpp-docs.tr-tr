---
title: remove_pointer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::remove_pointer
dev_langs:
- C++
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e1a3e1aacbb35984525ebf6d8dbd055a5cbf7b2
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="removepointer-class"></a>remove_pointer Sınıfı

Türü işaretçiden türe ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct remove_pointer;

template <class T>
using remove_pointer_t = typename remove_pointer<T>::type;
```

### <a name="parameters"></a>Parametreler

`T` Değişiklik türü.

## <a name="remarks"></a>Açıklamalar

Örneği `remove_pointer<T>` bir değişiklik-türü tutan `T1` zaman `T` biçimidir `T1*`, `T1* const`, `T1* volatile`, veya `T1* const volatile`, aksi takdirde `T`.

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

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_pointer Sınıfı](../standard-library/add-pointer-class.md)<br/>

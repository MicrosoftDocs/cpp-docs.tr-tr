---
title: add_lvalue_reference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_lvalue_reference
ms.assetid: 9933afc2-ad0d-465d-98fe-7d547fa3efe2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46ca75850aede04d54dc659e3f29166ab91abdbf
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102635"
---
# <a name="addlvaluereference-class"></a>add_lvalue_reference sınıfı

Yaptığı türünden başvurusu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_lvalue_reference;

template <class T>
using add_lvalue_reference_t = typename add_lvalue_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricinin bir örneği bir değişiklik-tür tutar *T* varsa *T* bir lvalue başvurusuna, aksi halde kalır `T&`.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

using namespace std;
int main()
{
    int val = 0;
    add_lvalue_reference_t<int> p = (int&)val;
    p = p;  // to quiet "unused" warning
    cout << "add_lvalue_reference_t<int> == "
        << typeid(p).name() << endl;

    return (0);
}
```

```Output
add_lvalue_reference_t<int> == int
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_reference Sınıfı](../standard-library/remove-reference-class.md)<br/>

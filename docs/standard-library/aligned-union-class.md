---
title: aligned_union Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_union
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
ms.openlocfilehash: b9ffb4aff4d4d5667ab8d626ea13a21da94ca0c1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456458"
---
# <a name="alignedunion-class"></a>aligned_union Sınıfı

Bir birleştirme türünü ve gereken boyutu depolamak için yeterince büyük ve uygun şekilde hizalı bir POD türü sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Len, class... Types>
struct aligned_union;

template <std::size_t Len, class... Types>
using aligned_union_t = typename aligned_union<Len, Types...>::type;
```

### <a name="parameters"></a>Parametreler

*Tepe*\
Birleşimdeki en büyük türe ilişkin hizalama değeri.

*Türü*\
Temel alınan birleşimdeki ayrı türler.

## <a name="remarks"></a>Açıklamalar

Bir UNION 'yi başlatılmamış depolamada depolamak için gereken hizalama ve boyutu almak için şablon sınıfını kullanın. TypeDef `type` öğesi, *türlerde*listelenen herhangi bir türün depolanması için uygun bir pod türü adlandırır; minimum boyut *len*olur. Türündeki `alignment_value` statik`std::size_t` üye, *türlerde*listelenen tüm türlerin gereken en katı hizalamasını içerir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir UNION yerleştirmek için `aligned_union` hizalanmış yığın arabelleği ayırmak için nasıl kullanılacağını gösterir.

```cpp
// std__type_traits__aligned_union.cpp
#include <iostream>
#include <type_traits>

union U_type
{
    int i;
    float f;
    double d;
    U_type(float e) : f(e) {}
};

typedef std::aligned_union<16, int, float, double>::type aligned_U_type;

int main()
{
    // allocate memory for a U_type aligned on a 16-byte boundary
    aligned_U_type au;
    // do placement new in the aligned memory on the stack
    U_type* u = new (&au) U_type(1.0f);
    if (nullptr != u)
    {
        std::cout << "value of u->i is " << u->i << std::endl;
        // must clean up placement objects manually!
        u->~U_type();
    }
}
```

```Output
value of u->i is 1065353216
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[alignment_of Sınıfı](../standard-library/alignment-of-class.md)

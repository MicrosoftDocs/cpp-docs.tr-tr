---
title: aligned_union Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_union
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
ms.openlocfilehash: 1a26675879c50440a4955989aca178dbe5049fdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411116"
---
# <a name="alignedunion-class"></a>aligned_union Sınıfı

Bir birleşim türü ve gerekli boyutu depolamak için bir POD türü büyüklükte ve düzgün hizalanmış sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Len, class... Types>
struct aligned_union;

template <std::size_t Len, class... Types>
using aligned_union_t = typename aligned_union<Len, Types...>::type;
```

### <a name="parameters"></a>Parametreler

*Len*<br/>
Hizalama değeri en büyük birleşim türü için.

*Türler*<br/>
Temel alınan Birliği'ndeki farklı türler.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir birleşim başlatılmamış depolamada depolamak için gereken boyutu ve hizalama almak için kullanın. Üye typedef `type` adları bir POD türü listelenen herhangi bir türde depolama için uygun *türleri*; en küçük boyut *Len*. Statik üye `alignment_value` türü `std::size_t` , listelenen tüm türleri için gereken en katı hizalama içeren *türleri*.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `aligned_union` UNION yerleştirmek için bir hizalanmış bir yığın arabelleği ayrılamadı.

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

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[alignment_of Sınıfı](../standard-library/alignment-of-class.md)<br/>

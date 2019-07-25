---
title: aligned_storage Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_storage
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
ms.openlocfilehash: 8a4e907faa6175b9e03f5367d09501aaea388bce
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456474"
---
# <a name="alignedstorage-class"></a>aligned_storage Sınıfı

Düzgün hizalanmış tür sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Len, std::size_t Align>
struct aligned_storage;

template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>
using aligned_storage_t = typename aligned_storage<Len, Align>::type;
```

### <a name="parameters"></a>Parametreler

*Tepe*\
Nesne boyutu.

*Acaktır*\
Hizalanacak nesne.

## <a name="remarks"></a>Açıklamalar

Şablon üyesi typedef `type` , hizalama *hizalı* ve boyutu *len*bir pod türü için bir eş anlamlı. *Hizalama* , bazı tür `alignment_of<T>::value` `T`için veya varsayılan hizalamayla eşit olmalıdır.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

typedef std::aligned_storage<sizeof (int),
    std::alignment_of<double>::value>::type New_type;
int main()
    {
    std::cout << "alignment_of<int> == "
        << std::alignment_of<int>::value << std::endl;
    std::cout << "aligned to double == "
        << std::alignment_of<New_type>::value << std::endl;

    return (0);
    }
```

```Output
alignment_of<int> == 4
aligned to double == 8
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[alignment_of Sınıfı](../standard-library/alignment-of-class.md)

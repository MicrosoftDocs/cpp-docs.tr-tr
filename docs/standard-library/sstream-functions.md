---
title: '&lt;sstream &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 43fcffe12afe50a94f06a18e7ee06729bc85854e
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039904"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream &gt; işlevleri

[Kur](#sstream_swap)

## <a name="swap"></a><a name="sstream_swap"></a> Kur

İki nesne arasındaki değerleri değiş tokuş eder `sstream` .

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Bir nesneye başvuru `sstream` .

*Right*\
Bir nesneye başvuru `sstream` .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütülür `left.swap(right)` .

## <a name="see-also"></a>Ayrıca bkz.

[\<sstream>](../standard-library/sstream.md)

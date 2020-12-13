---
description: 'Daha fazla bilgi edinin: &lt; sstream &gt; işlevleri'
title: '&lt;sstream &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 81fd6f392ca1fde26cf150d8079650c748e670ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153843"
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

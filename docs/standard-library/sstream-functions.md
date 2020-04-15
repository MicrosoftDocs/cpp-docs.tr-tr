---
title: '&lt;sstream&gt; fonksiyonları'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: bdf7cd26b25680eb7e5270fdc8ae7dac0d10f70f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336649"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; fonksiyonları

||
|-|
|[Takas](#sstream_swap)|

## <a name="swap"></a><a name="sstream_swap"></a>Takas

İki `sstream` nesne arasındaki değerleri değiştirir.

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

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Bir `sstream` nesneye başvuru.|
|*Doğru*|Bir `sstream` nesneye başvuru.|

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütür. `left.swap(right)`

## <a name="see-also"></a>Ayrıca bkz.

[\<sstream>](../standard-library/sstream.md)

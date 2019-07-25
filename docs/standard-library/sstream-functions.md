---
title: '&lt;sstream&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 707d35123797b84b2b7cef1d1cfd9005e4becb1c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447536"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; işlevleri

||
|-|
|[Kur](#sstream_swap)|

## <a name="sstream_swap"></a>Kur

İki `sstream` nesne arasındaki değerleri değiş tokuş eder.

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
|*tarafta*|Bir `sstream` nesneye başvuru.|
|*Right*|Bir `sstream` nesneye başvuru.|

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütülür `left.swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<sstream >](../standard-library/sstream.md)

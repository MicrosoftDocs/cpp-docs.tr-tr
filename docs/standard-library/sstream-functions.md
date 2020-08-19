---
title: '&lt;sstream &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 722cba257b12bb753aaa61ac2f430df76c2ceb93
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560380"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream &gt; işlevleri

||
|-|
|[Kur](#sstream_swap)|

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

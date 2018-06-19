---
title: '&lt;sstream&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: f98e5fc9521165d5599f904975e348276f346ea4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853293"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; işlevleri

||
|-|
|[Değiştirme](#sstream_swap)|

## <a name="sstream_swap"></a>  Değiştirme

İkisi arasındaki değerleri alış verişleri `sstream` nesneleri.

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
|`left`|Başvuru bir `sstream` nesnesi.|
|`right`|Başvuru bir `sstream` nesnesi.|

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütür `left.swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<sstream >](../standard-library/sstream.md)<br/>

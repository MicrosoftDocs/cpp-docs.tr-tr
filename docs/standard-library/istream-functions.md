---
title: '&lt;istream&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: b590559b01bb8f5db21fca9f78d220d8bad5c27e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537650"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; işlevleri

|||
|-|-|
|[değiştirme](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  değiştirme

İki akışı nesneleri öğelerini birbiriyle değiştirir.

```cpp
template <class Elem, class Tr>
void swap(
    basic_istream<Elem, Tr>& left,
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>
void swap(
    basic_iostream<Elem, Tr>& left,
    basic_iostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Bir akış.

*sağ*<br/>
Bir akış.

## <a name="ws"></a>  ws

Boşluk stream'de atlar.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr*<br/>
Bir akış.

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

İşleyici ayıklar ve herhangi bir öğe çıkarır `ch` hangi [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **Elem**>> ( [getloc](../standard-library/ios-base-class.md#getloc)). **olan**( **ctype** \< **Elem**>:: **alanı**, **ch**) geçerlidir.

İşlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) öğeleri ayıklanırken dosya sonu karşılaştığında. Döndürür *_Istr*.

### <a name="example"></a>Örnek

Bkz: [işleci >>](../standard-library/istream-operators.md#op_gt_gt) kullanma örneği için `ws`.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream >](../standard-library/istream.md)<br/>

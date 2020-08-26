---
title: '&lt;IStream &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 6d1fede2726d3d8f5dd678b95fd7a22a301ea95a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840979"
---
# <a name="ltistreamgt-functions"></a>&lt;IStream &gt; işlevleri

[Kur](#istream_swap)\
[ws](#ws)

## <a name="swap"></a><a name="istream_swap"></a> Kur

İki Stream nesnesinin öğelerini değiş tokuş eder.

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

*tarafta*\
Bir akış.

*Right*\
Bir akış.

## <a name="ws"></a><a name="ws"></a> RW

Akıştaki boşluğu atlar.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr*\
Bir akış.

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

İşleici, `ch` [use_facet](../standard-library/basic-filebuf-class.md#open) <  **CType** \< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#getloc)) için tüm öğeleri ayıklar ve atar. **:**( **CType** \< **Elem**> :: **Space**, **ch**) true.

İşlev, öğelerin ayıklanması sırasında dosya sonuyla karşılaştığında [SetState](../standard-library/basic-ios-class.md#setstate)( **eofbit**) öğesini çağırır. *_Istr*döndürür.

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [operatör>>](../standard-library/istream-operators.md#op_gt_gt) `ws` .

## <a name="see-also"></a>Ayrıca bkz.

[\<istream>](../standard-library/istream.md)

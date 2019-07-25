---
title: '&lt;IStream&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: fc512558969bc25d2b16afa2b93219e13d0b28ca
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458762"
---
# <a name="ltistreamgt-functions"></a>&lt;IStream&gt; işlevleri

|||
|-|-|
|[Kur](#istream_swap)|[RW](#ws)|

## <a name="istream_swap"></a>Kur

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

## <a name="ws"></a>RW

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

İşleici, `ch` [use_facet](../standard-library/basic-filebuf-class.md#open)< **CType** \< **eled**> > ( [getloc](../standard-library/ios-base-class.md#getloc)) için tüm öğeleri ayıklar ve atar. **Şu** ( **CType** \< **eled**>:: **Space**, **ch**) true.

İşlev, öğelerin ayıklanması sırasında dosya sonuyla karşılaştığında [SetState](../standard-library/basic-ios-class.md#setstate)( **eofbit**) öğesini çağırır. *_Istr*döndürür.

### <a name="example"></a>Örnek

Kullanım`ws`örneği için bkz. [operator > >](../standard-library/istream-operators.md#op_gt_gt) .

## <a name="see-also"></a>Ayrıca bkz.

[\<IStream >](../standard-library/istream.md)

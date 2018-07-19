---
title: '&lt;istream&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1193e7ab65c49f0f79aeae52ca6563310296116d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953654"
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

*Sol* bir akış.

*doğru* bir akış.

## <a name="ws"></a>  ws

Boşluk stream'de atlar.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr* bir akış.

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

İşleyici ayıklar ve herhangi bir öğe çıkarır `ch` hangi [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **Elem**>> ( [getloc](../standard-library/ios-base-class.md#getloc)). **olan**( **ctype** \< **Elem**>:: **alanı**, **ch**) geçerlidir.

İşlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) öğeleri ayıklanırken dosya sonu karşılaştığında. Döndürür *_Istr*.

### <a name="example"></a>Örnek

Bkz: [işleci >>](../standard-library/istream-operators.md#op_gt_gt) kullanma örneği için `ws`.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream >](../standard-library/istream.md)<br/>

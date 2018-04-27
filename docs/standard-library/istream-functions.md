---
title: '&lt;istream&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fa27845c84103ac1a0bd751871fdc97449a7f9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; işlevleri

|||
|-|-|
|[Değiştirme](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  Değiştirme

İki akışı nesneleri öğelerini değiş tokuş eder.

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

`left` Bir akış.

`right` Bir akış.

## <a name="ws"></a>  ws

Boşluk akışında atlar.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Parametreler

`_Istr` Bir akış.

### <a name="return-value"></a>Dönüş Değeri

Akış.

### <a name="remarks"></a>Açıklamalar

Manipulator ayıklar ve herhangi bir öğe atar `ch` kendisi için [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **Elem**>> ( [getloc](../standard-library/ios-base-class.md#getloc)). **olan**( **ctype** \< **Elem**>:: **alanı**, **ch**) geçerlidir.

İşlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) öğeleri ayıklanırken dosya sonu karşılaştığında. Döndürdüğü `_Istr`.

### <a name="example"></a>Örnek

Bkz: [işleci >>](../standard-library/istream-operators.md#op_gt_gt) kullanma örneği için `ws`.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream >](../standard-library/istream.md)<br/>

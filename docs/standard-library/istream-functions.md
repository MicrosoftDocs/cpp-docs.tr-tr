---
title: '&lt;istream&gt; fonksiyonları'
ms.date: 11/04/2016
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
ms.openlocfilehash: 3d647c7b05a3868ec0359410cc0e703306b874ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363073"
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; fonksiyonları

|||
|-|-|
|[Takas](#istream_swap)|[ws](#ws)|

## <a name="swap"></a><a name="istream_swap"></a>Takas

İki akış nesnesinin öğelerini değiştirir.

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

*Sol*\
Bir dere.

*Doğru*\
Bir dere.

## <a name="ws"></a><a name="ws"></a>Ws

Akıştaki beyaz alanı atlar.

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr*\
Bir dere.

### <a name="return-value"></a>Dönüş Değeri

Dere.

### <a name="remarks"></a>Açıklamalar

Manipülatör,**ctype** \< **Elem'i**> > `ch` [(getloc)](../standard-library/ios-base-class.md#getloc) [use_facet](../standard-library/basic-filebuf-class.md#open)< herhangi bir öğeyi ayıklar ve atar. **(** **ctype** \< **Elem**>:: **uzay**, **ch**) doğrudur.

İşlev, öğeleri ayıklarken dosyanın sonuyla karşılaşırsa [setstate](../standard-library/basic-ios-class.md#setstate) **(eofbit)** çağırır. *_Istr*döndürür.

### <a name="example"></a>Örnek

Kullanma örneği için>>`ws` [işleç](../standard-library/istream-operators.md#op_gt_gt) bkz.

## <a name="see-also"></a>Ayrıca bkz.

[\<istream>](../standard-library/istream.md)

---
title: '&lt;forward_list&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 1ddfb56c7ff68ec10c7bb56af3495e4042acb83c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421795"
---
# <a name="ltforward_listgt-operators"></a>&lt;forward_list&gt; işleçleri

## <a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi, sınıf şablonu `forward_list`iki nesnesini karşılaştırmak için `operator==` aşırı yükler. İşlev `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`döndürür.

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

listeler eşitse **true** ; listeler eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `!(left == right)`döndürür.

## <a name="op_lt"></a>işleç&lt;

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileriye doğru liste nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeye eşit ancak bundan küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi, sınıf şablonu `forward_list`iki nesnesini karşılaştırmak için `operator<` aşırı yükler. İşlev `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`döndürür.

## <a name="op_lt_eq"></a>işleç&lt;=

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden daha küçükse veya eşitse **doğru** . Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `!(right < left)`döndürür.

## <a name="op_gt"></a>işleç&gt;

İşlecin sol tarafındaki ileri liste nesnesinin, sağ taraftaki ileri liste nesnesinden daha büyük olup olmadığını sınar.

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden büyükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `right < left`döndürür.

## <a name="op_gt_eq"></a>işleç&gt;=

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

işlecin sol tarafındaki ileri listesinin, işlecin sağ tarafındaki ileri listesinden büyük veya ona eşit olması durumunda **doğru** . Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `!(left < right)`döndürür.

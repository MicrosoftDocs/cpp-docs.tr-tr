---
description: 'Daha fazla bilgi edinin: &lt; forward_list &gt; işleçleri'
title: '&lt;forward_list &gt; işleçleri'
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
ms.openlocfilehash: 39d3383e0489a544f65f18af3ff3c2b6d8f2e45d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232362"
---
# <a name="ltforward_listgt-operators"></a>&lt;forward_list &gt; işleçleri

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `operator==` , sınıf şablonunun iki nesnesini karşılaştırmak için aşırı yükler `forward_list` . İşlev döndürür `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())` .

## <a name="operator"></a><a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** listeler eşitse; **`false`** listeler eşitse.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi döndürür `!(left == right)` .

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileriye doğru liste nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeye eşit ancak ondan küçükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `operator<` , sınıf şablonunun iki nesnesini karşılaştırmak için aşırı yükler `forward_list` . İşlev döndürür `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())` .

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesinden küçük veya ona eşit olup olmadığını sınar.

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste işlecin sağ tarafındaki listeden daha küçükse veya eşitse, Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi döndürür `!(right < left)` .

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

İşlecin sol tarafındaki ileri liste nesnesinin, sağ taraftaki ileri liste nesnesinden daha büyük olup olmadığını sınar.

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki liste, işlecin sağ tarafındaki listeden büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi döndürür `right < left` .

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

İşlecin sol tarafındaki ileri liste nesnesinin sağ taraftaki ileri liste nesnesinden büyük veya ona eşit olup olmadığını sınar.

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** işlecin sol tarafındaki ileri listesi, işlecin sağ tarafındaki ileri listesinden daha büyükse veya eşitse, Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `!(left < right)` .

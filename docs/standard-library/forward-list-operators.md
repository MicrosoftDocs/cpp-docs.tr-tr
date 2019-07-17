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
ms.openlocfilehash: 64a49273cafd72158f176ee34ec271557ebee097
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240656"
---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; işleçleri

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki iletme liste nesnesi işlecin sağ tarafındaki iletme liste nesnesi eşit olup olmadığını sınar.

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `forward_list`.

*sağ*\
Bir nesne türü `forward_list`.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi aşırı `operator==` şablon sınıfının iki nesneleri karşılaştırmak için `forward_list`. İşlev döndürür `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`.

## <a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki iletme liste nesnesi işlecin sağ tarafındaki iletme liste nesnesi eşit olup olmadığını sınar.

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `forward_list`.

*sağ*\
Bir nesne türü `forward_list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** listeleri eşit; değilse, **false** listeleri aynıysa.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevinin döndürdüğü `!(left == right)`.

## <a name="op_lt"></a> İşleci&lt;

İşlecin sol tarafındaki iletme liste nesnesi işlecin sağ tarafındaki iletme listesi nesneden küçük olup olmadığını sınar.

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `forward_list`.

*sağ*\
Bir nesne türü `forward_list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin daha ancak değil işlecin sağ tarafındaki listenin eşit Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi aşırı `operator<` şablon sınıfının iki nesneleri karşılaştırmak için `forward_list`. İşlev döndürür `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`.

## <a name="op_lt_eq"></a> İşleci&lt;=

İşlecinin sol tarafında iletme liste nesnesi küçük olup olmadığını sınar veya işlecin sağ tarafındaki iletme liste nesnesi eşittir.

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `forward_list`.

*sağ*\
Bir nesne türü `forward_list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin daha veya işlecin sağ tarafındaki listenin eşittir; Aksi takdirde küçükse **false**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevinin döndürdüğü `!(right < left)`.

## <a name="op_gt"></a> İşleci&gt;

İşlecin sol tarafındaki iletme liste nesnesi iletme liste nesnesi işlecin sağ tarafındaki büyük olup olmadığını sınar.

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `forward_list`.

*sağ*\
Bir nesne türü `forward_list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** işlecinin sol tarafındaki listenin ise, aksi takdirde listede bir işlecin sağ tarafındaki büyük **false**.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevinin döndürdüğü `right < left`.

## <a name="op_gt_eq"></a> İşleci&gt;=

İşlecin sol tarafındaki iletme liste nesnesi büyük veya işlecin sağ tarafındaki iletme Liste nesnesine eşit olup olmadığını sınar.

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `forward_list`.

*sağ*\
Bir nesne türü `forward_list`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** iletme listenin işlecinin sol tarafındaki büyük veya eşit işlecin sağ tarafındaki İleri listesine; tersi durumda ise **false**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `!(left < right)`.

---
title: '&lt;system_error&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 5cf6a455beb5654ef65f7411db4783a32c71d625
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246218"
---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt; işleçleri

## <a name="op_eq_eq"></a> işleç ==

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Eşitlik için test edilecek nesne.

*sağ*\
Eşitlik için test edilecek nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse; **false** nesneler eşit değilse.

### <a name="remarks"></a>Açıklamalar

Bu işlev döndürür `left.category() == right.category() && left.value() == right.value()`.

## <a name="op_neq"></a> işleç! =

İşlecin sol tarafındaki nesne işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Eşitsizlik için test edilecek nesne.

*sağ*\
Eşitsizlik için test edilecek nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesne iletilmezse *sol* geçirilen nesne eşit değil *doğru*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev döndürür `!(left == right)`.

## <a name="op_lt"></a> İşleci&lt;

Bir nesnenin karşılaştırma için içeri geçirilen nesneden küçük olup olmadığını sınar.

```cpp
template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```

### <a name="parameters"></a>Parametreler

*Sol*\
Karşılaştırılacak nesne.

*sağ*\
Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesne iletilmezse *sol* nesneden değerinden *doğru*; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev hata sıralamasını sınar.

## <a name="op_ostream"></a> İşleci&lt;&lt;

```cpp
template <class charT, class traits> 
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```

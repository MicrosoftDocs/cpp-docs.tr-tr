---
title: '&lt;system_error &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 5ddd9135749c2dcfd40cd06a9b69cff65b1a8c8d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232878"
---
# <a name="ltsystem_errorgt-operators"></a>&lt;system_error &gt; işleçleri

## <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Eşitlik için sınanacak nesne.

*Right*\
Eşitlik için sınanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse; **`false`** Eğer nesneler eşitse.

### <a name="remarks"></a>Açıklamalar

Bu işlev döndürür `left.category() == right.category() && left.value() == right.value()` .

## <a name="operator"></a><a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Eşitsizlik için test edilecek nesne.

*Right*\
Eşitsizlik için test edilecek nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`***solda* geçirilen nesne, *sağa*geçirilen nesneye eşit değilse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlev döndürür `!(left == right)` .

## <a name="operatorlt"></a><a name="op_lt"></a>işlecinde&lt;

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

*tarafta*\
Karşılaştırılacak nesne.

*Right*\
Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`***solda* geçirilen nesne *sağdaki*nesneden küçükse; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işlev hata sıralamasını sınar.

## <a name="operatorltlt"></a><a name="op_ostream"></a>işlecinde&lt;&lt;

```cpp
template <class charT, class traits>
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```

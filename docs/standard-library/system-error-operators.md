---
title: '&lt;system_error&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 5cf6a455beb5654ef65f7411db4783a32c71d625
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420731"
---
# <a name="ltsystem_errorgt-operators"></a>&lt;system_error&gt; işleçleri

## <a name="op_eq_eq"></a>işleç = =

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

*sol*\
Eşitlik için sınanacak nesne.

*sağ*\
Eşitlik için sınanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

nesneler eşitse **true** ; nesneler eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Bu işlev `left.category() == right.category() && left.value() == right.value()`döndürür.

## <a name="op_neq"></a>işleç! =

İşlecin sol tarafındaki nesnenin sağ taraftaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
Eşitsizlik için test edilecek nesne.

*sağ*\
Eşitsizlik için test edilecek nesne.

### <a name="return-value"></a>Dönüş Değeri

*solda* geçirilen nesne, *sağa*geçirilen nesneye eşit değilse **doğru** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlev `!(left == right)`döndürür.

## <a name="op_lt"></a>işleç&lt;

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

*sol*\
Karşılaştırılacak nesne.

*sağ*\
Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

*solda* geçirilen nesne *sağdaki*nesneden küçükse **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev hata sıralamasını sınar.

## <a name="op_ostream"></a>işleç&lt;&lt;

```cpp
template <class charT, class traits> 
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```

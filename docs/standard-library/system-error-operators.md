---
title: '&lt;system_error&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 974b1294f8ef23936d79e64926595779a9019368
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963699"
---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&lt;](#op_lt)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a>  işleç ==

İşlecin sol tarafındaki nesnesinin işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Eşitlik için test edilecek nesne.|
|*sağ*|Eşitlik için test edilecek nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse; **false** nesneler eşit değilse.

### <a name="remarks"></a>Açıklamalar

Bu işlev döndürür `left.category() == right.category() && left.value() == right.value()`.

## <a name="op_neq"></a>  işleç! =

İşlecin sol tarafındaki nesne işlecin sağ tarafındaki nesneye eşit olup olmadığını sınar.

```cpp
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Eşitsizlik için test edilecek nesne.|
|*sağ*|Eşitsizlik için test edilecek nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesne iletilmezse *sol* geçirilen nesne eşit değil *doğru*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev döndürür `!(left == right)`.

## <a name="op_lt"></a>  İşleci&lt;

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

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Karşılaştırılacak nesne.|
|*sağ*|Karşılaştırılacak nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesne iletilmezse *sol* nesneden değerinden *doğru*; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlev hata sıralamasını sınar.

## <a name="see-also"></a>Ayrıca bkz.

[<system_error>](../standard-library/system-error.md)<br/>

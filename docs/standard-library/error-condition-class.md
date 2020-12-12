---
description: 'Hakkında daha fazla bilgi edinin: error_condition sınıfı'
title: error_condition Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
helpviewer_keywords:
- std::error_condition
- std::error_condition::value_type
- std::error_condition::assign
- std::error_condition::category
- std::error_condition::clear
- std::error_condition::message
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
ms.openlocfilehash: 6567a4406271147eadfdc9e9443ba333d931afba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232687"
---
# <a name="error_condition-class"></a>error_condition Sınıfı

Kullanıcı tanımlı hata kodlarını temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class error_condition;
```

## <a name="remarks"></a>Açıklamalar

Türünde bir nesne `error_condition` , bir hata kodu değerini ve bir nesne işaretçisini, Kullanıcı tanımlı hatalar için kullanılan hata kodları [kategorisini](../standard-library/error-category-class.md) temsil eden bir nesneye bir işaretçi halinde depolar.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[error_condition](#error_condition)|Türünde bir nesne oluşturur `error_condition` .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[assign (atamak)](#assign) |Bir hata koşuluna bir hata kodu değeri ve kategorisi atar.|
|[alan](#category)|Hata kategorisini döndürür.|
|[lediğiniz](#clear)|Hata kodu değerini ve kategorisini temizler.|
|[İleti](#message)|Hata kodunun adını döndürür.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç = =](#op_eq_eq)|Nesneler arasındaki eşitlik için testler `error_condition` .|
|[işleç! =](#op_neq)|Nesneler arasında eşitsizlik için testler `error_condition` .|
|[işleç<](#op_lt)|`error_condition`Nesnenin `error_code` karşılaştırma için geçirilen nesneden daha az olup olmadığını sınar.|
|[işleç =](#op_eq)|Nesnesine yeni bir numaralandırma değeri atar `error_condition` .|
|[işleç bool](#op_bool)|Türünde bir değişken yayınlar `error_condition` .|

### <a name="assign"></a><a name="assign"></a> ata

Bir hata koşuluna bir hata kodu değeri ve kategorisi atar.

```cpp
void assign(value_type val, const error_category& _Cat);
```

#### <a name="parameters"></a>Parametreler

*Acil*\
İçinde depolanacak hata kodu değeri `error_code` .

*_Cat*\
İçinde depolanacak hata kategorisi `error_code` .

#### <a name="remarks"></a>Açıklamalar

Üye işlevi, değer olarak *Val* 'yi hata kodu değeri ve *_Cat* bir işaretçi olarak depolar.

### <a name="category"></a><a name="category"></a> alan

Hata kategorisini döndürür.

```cpp
const error_category& category() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Depolanan hata kategorisine yönelik bir başvuru

#### <a name="remarks"></a>Açıklamalar

### <a name="clear"></a><a name="clear"></a> lediğiniz

Hata kodu değerini ve kategorisini temizler.

```cpp
clear();
```

#### <a name="remarks"></a>Açıklamalar

Üye işlevi sıfır hata kodu değerini ve [generic_category](../standard-library/system-error-functions.md#generic_category) nesnesine bir işaretçi depolar.

### <a name="error_condition"></a><a name="error_condition"></a> error_condition

Türünde bir nesne oluşturur `error_condition` .

```cpp
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Parametreler

*Acil*\
İçinde depolanacak hata kodu değeri `error_condition` .

*_Cat*\
İçinde depolanacak hata kategorisi `error_condition` .

*_Errcode*\
İçinde depolanacak numaralandırma değeri `error_condition` .

#### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu sıfır hata kodu değeri ve [generic_category](../standard-library/system-error-functions.md#generic_category)bir işaretçi depolar.

İkinci Oluşturucu, değer olarak *Val* 'yi hata kodu değeri ve [error_category](../standard-library/error-category-class.md)bir işaretçi olarak depolar.

Üçüncü Oluşturucu, `(value_type)_Errcode` hata kodu değeri olarak depolar ve [generic_category](../standard-library/system-error-functions.md#generic_category)bir işaretçisi.

### <a name="message"></a><a name="message"></a> İleti

Hata kodunun adını döndürür.

```cpp
string message() const;
```

#### <a name="return-value"></a>Dönüş Değeri

`string`Hata kodunun adını temsil eden.

#### <a name="remarks"></a>Açıklamalar

Bu üye işlev döndürür `category().message(value())` .

### <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

Nesneler arasındaki eşitlik için testler `error_condition` .

```cpp
bool operator==(const error_condition& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Eşitlik için test edilecek Ojbect.

#### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse; **`false`** Eğer nesneler eşitse.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() == right.category() && value == right.value()` .

### <a name="operator"></a><a name="op_neq"></a> işleç! =

Nesneler arasında eşitsizlik için testler `error_condition` .

```cpp
bool operator!=(const error_condition& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Eşitsizlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**`true`**`error_condition`nesne `error_condition` *sağa* geçirilen nesneye eşit değilse, tersi durumda **`false`** .

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `!(*this == right)` .

### <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

`error_condition`Nesnenin `error_code` karşılaştırma için geçirilen nesneden daha az olup olmadığını sınar.

```cpp
bool operator<(const error_condition& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
`error_condition`Karşılaştırılacak nesne.

#### <a name="return-value"></a>Dönüş Değeri

**`true`**`error_condition`nesne `error_condition` karşılaştırma için geçirilen nesneden küçükse; Aksi takdirde, **`false`** .

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() < right.category() || category() == right.category() && value < right.value()` .

### <a name="operator"></a><a name="op_eq"></a> işleç =

Nesnesine yeni bir numaralandırma değeri atar `error_condition` .

```cpp
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
    operator=(Enum _Errcode);
```

#### <a name="parameters"></a>Parametreler

*_Errcode*\
Nesneye atanacak numaralandırma değeri `error_condition` .

#### <a name="return-value"></a>Dönüş Değeri

`error_condition`Üye işlevi tarafından yeni numaralandırma değerine atanmakta olan nesneye bir başvuru.

#### <a name="remarks"></a>Açıklamalar

Üye işleci, `(value_type)error` hata kodu değeri ve [generic_category](../standard-library/system-error-functions.md#generic_category)işaretçisi olarak depolar. Döndürür **`*this`** .

### <a name="operator-bool"></a><a name="op_bool"></a> işleç bool

Türünde bir değişken yayınlar `error_condition` .

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Nesnenin Boolean değeri `error_condition` .

#### <a name="remarks"></a>Açıklamalar

İşleci **`true`** yalnızca [değeri](#value) sıfıra eşit değilse, dönüştürülebilir bir değer döndürür. Dönüş türü, türüne **`bool`** değil, `void *` veya diğer bilinen skalar türlere dönüştürülebilir.

### <a name="value"></a><a name="value"></a> deeri

Depolanan hata kodu değerini döndürür.

```cpp
value_type value() const;
```

#### <a name="return-value"></a>Dönüş Değeri

[Value_type](#value_type)türünde depolanan hata kodu değeri.

#### <a name="remarks"></a>Açıklamalar

### <a name="value_type"></a><a name="value_type"></a> value_type

Depolanan hata kodu değerini temsil eden bir tür.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür tanımı için bir eş anlamlı **`int`** .

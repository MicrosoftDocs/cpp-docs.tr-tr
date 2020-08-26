---
title: error_code Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
helpviewer_keywords:
- std::error_code
- std::error_code::value_type
- std::error_code::assign
- std::error_code::category
- std::error_code::clear
- std::error_code::default_error_condition
- std::error_code::message
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
ms.openlocfilehash: 5bbd67d2967a1a6d070ece54ea464a2a5a2deac9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844463"
---
# <a name="error_code-class"></a>error_code Sınıfı

Uygulamaya özgü olan alt düzey sistem hatalarını temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class error_code;
```

## <a name="remarks"></a>Açıklamalar

Sınıf türündeki bir nesne bir `error_code` hata kodu değerini ve rapor alt düzey sistem hatalarını tanımlayan bir hata kodları [kategorisini](../standard-library/error-category-class.md) temsil eden bir nesne işaretçisi depolar.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[error_code](#error_code)|Türünde bir nesne oluşturur `error_code` .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[assign (atamak)](#assign) |Hata koduna bir hata kodu değeri ve kategorisi atar.|
|[alan](#category)|Hata kategorisini döndürür.|
|[lediğiniz](#clear)|Hata kodu değerini ve kategorisini temizler.|
|[default_error_condition](#default_error_condition)|Varsayılan hata koşulunu döndürür.|
|[İleti](#message)|Hata kodunun adını döndürür.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç = =](#op_eq_eq)|Nesneler arasındaki eşitlik için testler `error_code` .|
|[işleç! =](#op_neq)|Nesneler arasında eşitsizlik için testler `error_code` .|
|[işleç<](#op_lt)|`error_code`Nesnenin `error_code` karşılaştırma için geçirilen nesneden daha az olup olmadığını sınar.|
|[işleç =](#op_eq)|Nesnesine yeni bir numaralandırma değeri atar `error_code` .|
|[işleç bool](#op_bool)|Türünde bir değişken yayınlar `error_code` .|

### <a name="assign"></a><a name="assign"></a> ata

Hata koduna bir hata kodu değeri ve kategorisi atar.

```cpp
void assign(value_type val, const error_category& _Cat);
```

#### <a name="parameters"></a>Parametreler

*Acil*\
İçinde depolanacak hata kodu değeri `error_code` .

*_Cat*\
İçinde depolanacak hata kategorisi `error_code` .

#### <a name="remarks"></a>Açıklamalar

Üye işlevi, değer olarak *Val* 'yi hata kodu değeri ve *_Cat*bir işaretçi olarak depolar.

### <a name="category"></a><a name="category"></a> alan

Hata kategorisini döndürür.

```cpp
const error_category& category() const;
```

#### <a name="remarks"></a>Açıklamalar

### <a name="clear"></a><a name="clear"></a> lediğiniz

Hata kodu değerini ve kategorisini temizler.

```cpp
clear();
```

#### <a name="remarks"></a>Açıklamalar

Üye işlevi sıfır hata kodu değerini ve [generic_category](../standard-library/system-error-functions.md#generic_category) nesnesine bir işaretçi depolar.

### <a name="default_error_condition"></a><a name="default_error_condition"></a> default_error_condition

Varsayılan hata koşulunu döndürür.

```cpp
error_condition default_error_condition() const;
```

#### <a name="return-value"></a>Dönüş Değeri

[Default_error_condition](../standard-library/error-category-class.md#default_error_condition)tarafından belirtilen [error_condition](../standard-library/error-condition-class.md) .

#### <a name="remarks"></a>Açıklamalar

Bu üye işlev döndürür `category().default_error_condition(value())` .

### <a name="error_code"></a><a name="error_code"></a> error_code

Türünde bir nesne oluşturur `error_code` .

```cpp
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Parametreler

*Acil*\
İçinde depolanacak hata kodu değeri `error_code` .

*_Cat*\
İçinde depolanacak hata kategorisi `error_code` .

*_Errcode*\
İçinde depolanacak numaralandırma değeri `error_code` .

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

Nesneler arasındaki eşitlik için testler `error_code` .

```cpp
bool operator==(const error_code& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Eşitlik için sınanacak nesne.

#### <a name="return-value"></a>Dönüş Değeri

**`true`** nesneler eşitse; **`false`** Eğer nesneler eşitse.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() == right.category() && value == right.value()` .

### <a name="operator"></a><a name="op_neq"></a> işleç! =

Nesneler arasında eşitsizlik için testler `error_code` .

```cpp
bool operator!=(const error_code& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Eşitsizlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**`true`**`error_code`nesne `error_code` *sağa*geçirilen nesneye eşit değilse, tersi durumda **`false`** .

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `!(*this == right)` .

### <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

`error_code`Nesnenin `error_code` karşılaştırma için geçirilen nesneden daha az olup olmadığını sınar.

```cpp
bool operator<(const error_code& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırılacak error_code nesnesi.

#### <a name="return-value"></a>Dönüş Değeri

**`true`**`error_code`nesne `error_code` karşılaştırma için geçirilen nesneden küçükse; Aksi takdirde, **`false`** .

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() < right.category() || category() == right.category() && value < right.value()` .

### <a name="operator"></a><a name="op_eq"></a> işleç =

Nesnesine yeni bir numaralandırma değeri atar `error_code` .

```cpp
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value, error_code>::type&
    operator=(_Enum _Errcode);
```

#### <a name="parameters"></a>Parametreler

*_Errcode*\
Nesneye atanacak numaralandırma değeri `error_code` .

#### <a name="return-value"></a>Dönüş Değeri

`error_code`Üye işlevi tarafından yeni numaralandırma değerine atanmakta olan nesneye bir başvuru.

#### <a name="remarks"></a>Açıklamalar

Üye işleci, `(value_type)_Errcode` hata kodu değeri ve [generic_category](../standard-library/system-error-functions.md#generic_category)işaretçisi olarak depolar. Döndürür **`*this`** .

### <a name="operator-bool"></a><a name="op_bool"></a> işleç bool

Türünde bir değişken yayınlar `error_code` .

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Nesnenin Boolean değeri `error_code` .

#### <a name="remarks"></a>Açıklamalar

İşleci **`true`** yalnızca [değeri](#value) sıfıra eşit değilse, dönüştürülebilir bir değer döndürür. Dönüş türü, türüne **`bool`** değil, `void *` veya diğer bilinen skalar türlere dönüştürülebilir.

### <a name="value"></a><a name="value"></a> deeri

Depolanan hata kodu değerini döndürür.

```cpp
value_type value() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Value_type](#value_type)türünde depolanan hata kodu değeri.

### <a name="value_type"></a><a name="value_type"></a> value_type

Depolanan hata kodu değerini temsil eden bir tür.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Açıklamalar

Bu tür tanımı için bir eş anlamlı **`int`** .

---
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
ms.openlocfilehash: cbadf6a22871cc9a23d37c095a398490c8a4c72c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245794"
---
# <a name="errorcondition-class"></a>error_condition Sınıfı

Kullanıcı tanımlı hata kodları temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class error_condition;
```

## <a name="remarks"></a>Açıklamalar

Türünde bir nesne `error_condition` bir hata kodu değeri ve temsil eden bir nesne için bir işaretçi depolayan bir [kategori](../standard-library/error-category-class.md) hata kodları için kullanılan kullanıcı tanımlı hata bildirdi.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[error_condition](#error_condition)|Türünde bir nesne oluşturur `error_condition`.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Ata](#assign)|Bir hata kodu değeri ve kategori için bir hata durumu atar.|
|[Kategori](#category)|Hata kategorisi döndürür.|
|[Temizle](#clear)|Hata kodu değerini ve kategorisini temizler.|
|[message](#message)|Hata kodu adını döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](#op_eq_eq)|Arasındaki eşitliği sınar `error_condition` nesneleri.|
|[operator!=](#op_neq)|Arasındaki eşitsizliği sınar `error_condition` nesneleri.|
|[işleç <](#op_lt)|Olmadığını test eder `error_condition` nesne küçüktür `error_code` nesnesi geçirildi karşılaştırma için.|
|[operator=](#op_eq)|İçin yeni bir sabit listesi değeri atar `error_condition` nesne.|
|[bool işleci](#op_bool)|Türünde bir değişken bıraktığı `error_condition`.|

### <a name="assign"></a> Ata

Bir hata kodu değeri ve kategori için bir hata durumu atar.

```cpp
void assign(value_type val, const error_category& _Cat);
```

#### <a name="parameters"></a>Parametreler

*VAL*\
Hata kodu değeri depolamak için `error_code`.

*_Cat*\
Depolamak için hata kategorisi `error_code`.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi depoları *val* hata kodu değeri ve bir işaretçi olarak *_Cat*.

### <a name="category"></a> Kategori

Hata kategorisi döndürür.

```cpp
const error_category& category() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Depolanan hata kategorisi için başvuru

#### <a name="remarks"></a>Açıklamalar

### <a name="clear"></a> Temizle

Hata kodu değerini ve kategorisini temizler.

```cpp
clear();
```

#### <a name="remarks"></a>Açıklamalar

Üye işlevi bir sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category) nesne.

### <a name="error_condition"></a> error_condition

Türünde bir nesne oluşturur `error_condition`.

```cpp
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Parametreler

*VAL*\
Hata kodu değeri depolamak için `error_condition`.

*_Cat*\
Depolamak için hata kategorisi `error_condition`.

*_Errcode*\
Numaralandırma değeri depolamak için `error_condition`.

#### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category).

İkinci oluşturucu depoları *val* hata kodu değeri ve bir işaretçi olarak [error_category](../standard-library/error-category-class.md).

Üçüncü Oluşturucu depoları `(value_type)_Errcode` hata kodu değeri ve bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="message"></a> İleti

Hata kodu adını döndürür.

```cpp
string message() const;
```

#### <a name="return-value"></a>Dönüş Değeri

A `string` hata kodu adını temsil eden.

#### <a name="remarks"></a>Açıklamalar

Bu üye işlevinin döndürdüğü `category().message(value())`.

### <a name="op_eq_eq"></a> işleç ==

Arasındaki eşitliği sınar `error_condition` nesneleri.

```cpp
bool operator==(const error_condition& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitlik için test edilecek ojbect.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse; **false** nesneler eşit değilse.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() == right.category() && value == right.value()`.

### <a name="op_neq"></a> işleç! =

Arasındaki eşitsizliği sınar `error_condition` nesneleri.

```cpp
bool operator!=(const error_condition& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitsizlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_condition` nesnesi eşit değil `error_condition` geçirilen nesne *doğru*; Aksi takdirde **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `!(*this == right)`.

### <a name="op_lt"></a> İşleci&lt;

Olmadığını test eder `error_condition` nesne küçüktür `error_code` nesnesi geçirildi karşılaştırma için.

```cpp
bool operator<(const error_condition& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
`error_condition` Karşılaştırılacak nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_condition` nesne küçüktür `error_condition` karşılaştırma için; geçirilen nesne Aksi takdirde, **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() < right.category() || category() == right.category() && value < right.value()`.

### <a name="op_eq"></a> işleç =

İçin yeni bir sabit listesi değeri atar `error_condition` nesne.

```cpp
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
    operator=(Enum _Errcode);
```

#### <a name="parameters"></a>Parametreler

*_Errcode*\
Numaralandırma değeri atamak için `error_condition` nesne.

#### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `error_condition` yeni sabit listesi değeri üye işlevi tarafından atanan nesne.

#### <a name="remarks"></a>Açıklamalar

Üye işleci depoları `(value_type)error` hata kodu değeri ve bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category). Döndürür `*this`.

### <a name="op_bool"></a> bool işleci

Türünde bir değişken bıraktığı `error_condition`.

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Boole değeri `error_condition` nesne.

#### <a name="remarks"></a>Açıklamalar

İşleci için bir değer dönüştürülebilir döndürür **true** yalnızca [değer](#value) sıfıra eşit değil. Dönüş türüne dönüştürülebilir yalnızca **bool**değil, `void *` veya bilinen diğer skaler türler.

### <a name="value"></a> Değer

Depolanan hata kodu değerini döndürür.

```cpp
value_type value() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Türü depolanan hata kodu değerini [value_type](#value_type).

#### <a name="remarks"></a>Açıklamalar

### <a name="value_type"></a> value_type

Depolanan hata kodu değerini temsil eden tür.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür tanımını eşanlamlıdır **int**.

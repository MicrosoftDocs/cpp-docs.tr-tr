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
ms.openlocfilehash: 919a2a81c66de9adf15deeae8cf8ff3dea08762e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245828"
---
# <a name="errorcode-class"></a>error_code Sınıfı

Uygulamaya özel alt düzey sistemi hataları temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class error_code;
```

## <a name="remarks"></a>Açıklamalar

Bir nesne türü `error_code` sınıfı, bir hata kodu değeri ve temsil eden bir nesne için bir işaretçi depolayan bir [kategori](../standard-library/error-category-class.md) hatasını açıklayan kodları alt düzey sistemi hataları bildirilen.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[error_code](#error_code)|Türünde bir nesne oluşturur `error_code`.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Ata](#assign)|Bir hata kodu değerini ve kategorisini bir hata koduna atar.|
|[Kategori](#category)|Hata kategorisi döndürür.|
|[Temizle](#clear)|Hata kodu değerini ve kategorisini temizler.|
|[default_error_condition](#default_error_condition)|Varsayılan hata durumunu döndürür.|
|[message](#message)|Hata kodu adını döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](#op_eq_eq)|Arasındaki eşitliği sınar `error_code` nesneleri.|
|[operator!=](#op_neq)|Arasındaki eşitsizliği sınar `error_code` nesneleri.|
|[işleç <](#op_lt)|Olmadığını test eder `error_code` nesne küçüktür `error_code` nesnesi geçirildi karşılaştırma için.|
|[operator=](#op_eq)|İçin yeni bir sabit listesi değeri atar `error_code` nesne.|
|[bool işleci](#op_bool)|Türünde bir değişken bıraktığı `error_code`.|

### <a name="assign"></a> Ata

Bir hata kodu değerini ve kategorisini bir hata koduna atar.

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

#### <a name="remarks"></a>Açıklamalar

### <a name="clear"></a> Temizle

Hata kodu değerini ve kategorisini temizler.

```cpp
clear();
```

#### <a name="remarks"></a>Açıklamalar

Üye işlevi bir sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category) nesne.

### <a name="default_error_condition"></a> default_error_condition

Varsayılan hata durumunu döndürür.

```cpp
error_condition default_error_condition() const;
```

#### <a name="return-value"></a>Dönüş Değeri

[Error_condition](../standard-library/error-condition-class.md) tarafından belirtilen [default_error_condition](../standard-library/error-category-class.md#default_error_condition).

#### <a name="remarks"></a>Açıklamalar

Bu üye işlevinin döndürdüğü `category().default_error_condition(value())`.

### <a name="error_code"></a> error_code

Türünde bir nesne oluşturur `error_code`.

```cpp
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Parametreler

*VAL*\
Hata kodu değeri depolamak için `error_code`.

*_Cat*\
Depolamak için hata kategorisi `error_code`.

*_Errcode*\
Numaralandırma değeri depolamak için `error_code`.

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

Arasındaki eşitliği sınar `error_code` nesneleri.

```cpp
bool operator==(const error_code& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse; **false** nesneler eşit değilse.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() == right.category() && value == right.value()`.

### <a name="op_neq"></a> işleç! =

Arasındaki eşitsizliği sınar `error_code` nesneleri.

```cpp
bool operator!=(const error_code& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitsizlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_code` nesnesi eşit değil `error_code` geçirilen nesne *doğru*; Aksi takdirde **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `!(*this == right)`.

### <a name="op_lt"></a> İşleci&lt;

Olmadığını test eder `error_code` nesne küçüktür `error_code` nesnesi geçirildi karşılaştırma için.

```cpp
bool operator<(const error_code& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Karşılaştırılacak error_code nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_code` nesne küçüktür `error_code` karşılaştırma için; geçirilen nesne Aksi takdirde, **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() < right.category() || category() == right.category() && value < right.value()`.

### <a name="op_eq"></a> işleç =

İçin yeni bir sabit listesi değeri atar `error_code` nesne.

```cpp
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value, error_code>::type&
    operator=(_Enum _Errcode);
```

#### <a name="parameters"></a>Parametreler

*_Errcode*\
Numaralandırma değeri atamak için `error_code` nesne.

#### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `error_code` yeni sabit listesi değeri üye işlevi tarafından atanan nesne.

#### <a name="remarks"></a>Açıklamalar

Üye işleci depoları `(value_type)_Errcode` hata kodu değeri ve bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category). Döndürür `*this`.

### <a name="op_bool"></a> bool işleci

Türünde bir değişken bıraktığı `error_code`.

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Boole değeri `error_code` nesne.

#### <a name="remarks"></a>Açıklamalar

İşleci için bir değer dönüştürülebilir döndürür **true** yalnızca [değer](#value) sıfıra eşit değil. Dönüş türüne dönüştürülebilir yalnızca **bool**değil, `void *` veya bilinen diğer skaler türler.

### <a name="value"></a> Değer

Depolanan hata kodu değerini döndürür.

```cpp
value_type value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türü depolanan hata kodu değerini [value_type](#value_type).

### <a name="value_type"></a> value_type

Depolanan hata kodu değerini temsil eden tür.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Açıklamalar

Bu tür tanımı eşanlamlıdır **int**.

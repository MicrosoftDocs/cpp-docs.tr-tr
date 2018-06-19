---
title: error_code sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
dev_langs:
- C++
helpviewer_keywords:
- std::error_code
- std::error_code::value_type
- std::error_code::assign
- std::error_code::category
- std::error_code::clear
- std::error_code::default_error_condition
- std::error_code::message
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44de89891f3380f71e4fa590626ba4e275782f9c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848043"
---
# <a name="errorcode-class"></a>error_code Sınıfı

Uygulamaya özel alt düzey sistem hataları temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class error_code;
```

## <a name="remarks"></a>Açıklamalar

Türünde bir nesne `error_code` sınıfı depolayan bir hata kodu değeri ve temsil eden bir nesne için bir işaretçi bir [kategori](../standard-library/error-category-class.md) hatasını açıklayan kodları alt düzey sistem hatalarını bildirdi.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[error_code](#error_code)|Türünde bir nesne oluşturur `error_code`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[value_type](#value_type)|Saklı hata kodu değerini temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Bir hata kodu değerini ve kategori için hata kodunu atar.|
|[Kategori](#category)|Hata kategorisi döndürür.|
|[Temizle](#clear)|Hata kodu değerini ve kategori temizler.|
|[default_error_condition](#default_error_condition)|Varsayılan hata koşulu döndürür.|
|[message](#message)|Hata kodu adını döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](#op_eq_eq)|Testler arasında eşitliği `error_code` nesneleri.|
|[operator!=](#op_neq)|Testler arasında eşitsizlik için `error_code` nesneleri.|
|[operator <](#op_lt)|Varsa testleri `error_code` nesne küçük `error_code` nesne geçirilen karşılaştırma için.|
|[operator=](#op_eq)|Yeni bir numaralandırma değeri atar `error_code` nesnesi.|
|[işleç bool değeri](#op_bool)|Türünde bir değişken bıraktığı `error_code`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<system_error >

**Namespace:** std

## <a name="assign"></a>  error_code::Assign

Bir hata kodu değerini ve kategori için hata kodunu atar.

```cpp
void assign(value_type val, const error_category& _Cat);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`val`|Hata kodu değeri depolamak için `error_code`.|
|`_Cat`|Hata kategorisi depolamak üzere `error_code`.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi depoları `val` hata kodu değerini gösteren bir işaretçi olarak `_Cat`.

## <a name="category"></a>  error_code::category

Hata kategorisi döndürür.

```cpp
const error_category& category() const;
```

### <a name="remarks"></a>Açıklamalar

## <a name="clear"></a>  error_code::Clear

Hata kodu değerini ve kategori temizler.

```cpp
clear();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category) nesnesi.

## <a name="default_error_condition"></a>  error_code::default_error_condition

Varsayılan hata koşulu döndürür.

```cpp
error_condition default_error_condition() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Error_condition](../standard-library/error-condition-class.md) tarafından belirtilen [default_error_condition](../standard-library/error-category-class.md#default_error_condition).

### <a name="remarks"></a>Açıklamalar

Bu üye işlevinin döndürdüğü `category().default_error_condition(value())`.

## <a name="error_code"></a>  error_code::error_code

Türünde bir nesne oluşturur `error_code`.

```cpp
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`val`|Hata kodu değeri depolamak için `error_code`.|
|`_Cat`|Hata kategorisi depolamak üzere `error_code`.|
|`_Errcode`|Numaralandırma değeri depolamak için `error_code`.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu sıfır hata kodu değeri ve bir işaretçi depolar [generic_category](../standard-library/system-error-functions.md#generic_category).

İkinci oluşturucu depoları `val` hata kodu değerini gösteren bir işaretçi olarak [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).

Üçüncü Oluşturucusu depoları `(value_type)_Errcode` hata kodu değerini gösteren bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category).

## <a name="message"></a>  error_code::Message

Hata kodu adını döndürür.

```cpp
string message() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `string` hata kodu adını temsil eden.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevinin döndürdüğü `category().message(value())`.

## <a name="op_eq_eq"></a>  error_code::operator ==

Testler arasında eşitliği `error_code` nesneleri.

```cpp
bool operator==(const error_code& right) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`right`|Eşitlik için test edilebilir nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneleri eşitse; **false** nesneleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() == right.category() && value == right.value()`.

## <a name="op_neq"></a>  error_code::operator! =

Testler arasında eşitsizlik için `error_code` nesneleri.

```cpp
bool operator!=(const error_code& right) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`right`|Eşitsizlik için test edilebilir nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_code` nesnesi eşit değil `error_code` nesnesi geçirildi `right`; Aksi halde **false**.

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `!(*this == right)`.

## <a name="op_lt"></a>  error_code::operator&lt;

Varsa testleri [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31) nesne küçük `error_code` nesne geçirilen karşılaştırma için.

```cpp
bool operator<(const error_code& right) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`right`|Karşılaştırılacak error_code nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_code` nesne küçük `error_code` karşılaştırma için; geçirilen nesnesi Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `category() < right.category() || category() == right.category() && value < right.value()`.

## <a name="op_eq"></a>  error_code::operator =

Yeni bir numaralandırma değeri atar [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31) nesnesi.

```cpp
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type&
 operator=(_Enum _Errcode);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`_Errcode`|Numaralandırma değeri atamak için `error_code` nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `error_code` yeni numaralandırma değeri üye işlevi tarafından atanan nesne.

### <a name="remarks"></a>Açıklamalar

Üye işleci depoları `(value_type)_Errcode` hata kodu değerini gösteren bir işaretçi olarak [generic_category](../standard-library/system-error-functions.md#generic_category). Döndürdüğü `*this`.

## <a name="op_bool"></a>  error_code::operator bool

Türünde bir değişken bıraktığı `error_code`.

```cpp
explicit operator bool() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boole değeri `error_code` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir değer dönüştürülebilir işleci döndürür `true` yalnızca [değeri](#value) sıfıra eşit değil. Dönüş türü yalnızca dönüştürülebilir `bool`, değil `void *` veya diğer bilinen skaler türler.

## <a name="value"></a>  error_code::Value

Saklı hata kodu değerini döndürür.

```cpp
value_type value() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türü depolanan hata kodu değeri [value_type](#value_type).

### <a name="remarks"></a>Açıklamalar

## <a name="value_type"></a>  error_code::value_type

Saklı hata kodu değerini temsil eden tür.

```cpp
typedef int value_type;
```

### <a name="remarks"></a>Açıklamalar

Bu tür tanımı için eş anlamlı olduğundan `int`.

## <a name="see-also"></a>Ayrıca bkz.

[error_category Sınıfı](../standard-library/error-category-class.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>

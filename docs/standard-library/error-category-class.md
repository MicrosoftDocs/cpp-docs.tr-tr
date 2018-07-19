---
title: error_category sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
dev_langs:
- C++
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f37029491c4a438f44c9f1bb27a9d192c14d1f12
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028235"
---
# <a name="errorcategory-class"></a>error_category Sınıfı

Nesneler için bir kategori hata kodlarının tanımlayan soyut, ortak temel temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class error_category;
```

## <a name="remarks"></a>Açıklamalar

İki önceden tanımlanmış nesneler uygulama `error_category`: [generic_category](../standard-library/system-error-functions.md#generic_category) ve [system_category](../standard-library/system-error-functions.md#system_category).

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[default_error_condition](#default_error_condition)|Bir hata koşulu nesnesi için hata kodu değerini depolar.|
|[eşdeğeri](#equivalent)|Hata nesneleri eşdeğer olup olmadığını belirten bir değeri döndürür.|
|[message](#message)|Belirtilen hata kodunun adı döndürür.|
|[Adı](#name)|Kategorinin adını döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](#op_eq_eq)|Arasındaki eşitliği sınar `error_category` nesneleri.|
|[operator!=](#op_neq)|Arasındaki eşitsizliği sınar `error_category` nesneleri.|
|[işleç <](#op_lt)|Olmadığını test eder [error_category](../standard-library/error-category-class.md) nesne küçüktür `error_category` nesnesi geçirildi karşılaştırma için.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<system_error >

**Namespace:** std

## <a name="default_error_condition"></a>  error_category::default_error_condition

Bir hata koşulu nesnesi için hata kodu değerini depolar.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Errval*|Hata kodu değeri depolamak için [error_condition](../standard-library/error-condition-class.md).|

### <a name="return-value"></a>Dönüş Değeri

Döndürür `error_condition(_Errval, *this)`.

### <a name="remarks"></a>Açıklamalar

## <a name="equivalent"></a>  error_category::equivalent

Hata nesneleri eşdeğer olup olmadığını belirten bir değeri döndürür.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Errval*|Hata kodu Karşılaştırılacak değer.|
|*_Cond*|[Error_condition](../standard-library/error-condition-class.md) Karşılaştırılacak nesne.|
|*_Kod*|[Error_code](../standard-library/error-code-class.md) Karşılaştırılacak nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** kategori ve değeri olması durumunda eşit; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür `*this == _Cond.category() && _Cond.value() == _Errval`.

İkinci üye işlevi döndürür `*this == _Code.category() && _Code.value() == _Errval`.

## <a name="message"></a>  error_category::Message

Belirtilen hata kodunun adı döndürür.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*VAL*|Açıklamak için hata kodu değeri.|

### <a name="return-value"></a>Dönüş Değeri

Hata kodunun açıklayıcı bir ad verir *val* kategorisi için.

### <a name="remarks"></a>Açıklamalar

## <a name="name"></a>  error_category::Name

Kategorinin adını döndürür.

```cpp
virtual const char *name() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kategori adı bayt null ile sonlandırılmış dize olarak döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="op_eq_eq"></a>  error_category::operator ==

Arasındaki eşitliği sınar `error_category` nesneleri.

```cpp
bool operator==(const error_category& right) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Eşitlik için test edilecek nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse; **false** nesneler eşit değilse.

### <a name="remarks"></a>Açıklamalar

Bu üye işleci döndürür `this == &right`.

## <a name="op_neq"></a>  error_category::operator! =

Arasındaki eşitsizliği sınar `error_category` nesneleri.

```cpp
bool operator!=(const error_category& right) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Eşitsizlik için test edilecek nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_category` nesnesi eşit değil `error_category` geçirilen nesne *doğru*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `(!*this == right)`.

## <a name="op_lt"></a>  error_category::operator&lt;

Olmadığını test eder [error_category](../standard-library/error-category-class.md) nesne küçüktür `error_category` nesnesi geçirildi karşılaştırma için.

```cpp
bool operator<(const error_category& right) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|`error_category` Karşılaştırılacak nesne.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_category` nesne küçüktür `error_category` karşılaştırma için; geçirilen nesne Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `this < &right`.

## <a name="value_type"></a>  error_category::value_type

Depolanan hata kodu değerini temsil eden tür.

```cpp
typedef int value_type;
```

### <a name="remarks"></a>Açıklamalar

Bu tür tanımı eşanlamlıdır **int**.

## <a name="see-also"></a>Ayrıca bkz.

[<system_error>](../standard-library/system-error.md)<br/>

---
title: error_category Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
ms.openlocfilehash: 308fa1a2309ddfda1a02fe6a687360185c1e7c6e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245849"
---
# <a name="errorcategory-class"></a>error_category Sınıfı

Nesneler için bir kategori hata kodlarının tanımlayan soyut, ortak temel temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class error_category;

constexpr error_category() noexcept;
virtual ~error_category();
error_category(const error_category&) = delete
```

## <a name="remarks"></a>Açıklamalar

İki önceden tanımlanmış nesneler uygulama `error_category`: [generic_category](../standard-library/system-error-functions.md#generic_category) ve [system_category](../standard-library/system-error-functions.md#system_category).

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[default_error_condition](#default_error_condition)|Bir hata koşulu nesnesi için hata kodu değerini depolar.|
|[eşdeğeri](#equivalent)|Hata nesneleri eşdeğer olup olmadığını belirten bir değeri döndürür.|
|[generic_category](#generic)||
|[message](#message)|Belirtilen hata kodunun adı döndürür.|
|[name](#name)|Kategorinin adını döndürür.|
|[system_category](#system)||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator=](#op_as)||
|[operator==](#op_eq_eq)|Arasındaki eşitliği sınar `error_category` nesneleri.|
|[operator!=](#op_neq)|Arasındaki eşitsizliği sınar `error_category` nesneleri.|
|[işleç <](#op_lt)|Olmadığını test eder [error_category](../standard-library/error-category-class.md) nesne küçüktür `error_category` nesnesi geçirildi karşılaştırma için.|

## <a name="default_error_condition"></a> default_error_condition

Bir hata koşulu nesnesi için hata kodu değerini depolar.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>Parametreler

*_Errval*\
Hata kodu değeri depolamak için [error_condition](../standard-library/error-condition-class.md).

### <a name="return-value"></a>Dönüş Değeri

Döndürür `error_condition(_Errval, *this)`.

### <a name="remarks"></a>Açıklamalar

### <a name="equivalent"></a> eşdeğeri

Hata nesneleri eşdeğer olup olmadığını belirten bir değeri döndürür.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

#### <a name="parameters"></a>Parametreler

*_Errval*\
Hata kodu Karşılaştırılacak değer.

*_Cond*\
[Error_condition](../standard-library/error-condition-class.md) Karşılaştırılacak nesne.

*_Kod*\
[Error_code](../standard-library/error-code-class.md) Karşılaştırılacak nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** kategori ve değeri olması durumunda eşit; Aksi takdirde **false**.

#### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür `*this == _Cond.category() && _Cond.value() == _Errval`.

İkinci üye işlevi döndürür `*this == _Code.category() && _Code.value() == _Errval`.

### <a name="generic"></a> generic_category

```cpp
const error_category& generic_category();
```

### <a name="message"></a> İleti

Belirtilen hata kodunun adı döndürür.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

#### <a name="parameters"></a>Parametreler

*VAL*\
Açıklamak için hata kodu değeri.

#### <a name="return-value"></a>Dönüş Değeri

Hata kodunun açıklayıcı bir ad verir *val* kategorisi için.

#### <a name="remarks"></a>Açıklamalar

### <a name="name"></a> Adı

Kategorinin adını döndürür.

```cpp
virtual const char *name() const = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Kategori adı bayt null ile sonlandırılmış dize olarak döndürür.

### <a name="op_as"></a> işleç =

```cpp
error_category& operator=(const error_category&) = delete;
```


### <a name="op_eq_eq"></a> işleç ==

Arasındaki eşitliği sınar `error_category` nesneleri.

```cpp
bool operator==(const error_category& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse; **false** nesneler eşit değilse.

#### <a name="remarks"></a>Açıklamalar

Bu üye işleci döndürür `this == &right`.

### <a name="op_neq"></a> işleç! =

Arasındaki eşitsizliği sınar `error_category` nesneleri.

```cpp
bool operator!=(const error_category& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitsizlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_category` nesnesi eşit değil `error_category` geçirilen nesne *doğru*; Aksi takdirde **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `(!*this == right)`.

### <a name="op_lt"></a> İşleci&lt;

Olmadığını test eder [error_category](../standard-library/error-category-class.md) nesne küçüktür `error_category` nesnesi geçirildi karşılaştırma için.

```cpp
bool operator<(const error_category& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
`error_category` Karşılaştırılacak nesne.

#### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `error_category` nesne küçüktür `error_category` karşılaştırma için; geçirilen nesne Aksi takdirde, **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci döndürür `this < &right`.

### <a name="system"></a> system_category

```cpp
const error_category& system_category();
```

### <a name="value_type"></a> value_type

Depolanan hata kodu değerini temsil eden tür.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Açıklamalar

Bu tür tanımı eşanlamlıdır **int**.

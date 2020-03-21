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
ms.openlocfilehash: 3ed2eceb60c2efa78181faea58a256b0e35d489f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076607"
---
# <a name="error_category-class"></a>error_category Sınıfı

Bir hata kodları kategorisini açıklayan nesneler için soyut, ortak temeli temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class error_category;

constexpr error_category() noexcept;
virtual ~error_category();
error_category(const error_category&) = delete
```

## <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış iki nesne `error_category`uygular: [generic_category](../standard-library/system-error-functions.md#generic_category) ve [system_category](../standard-library/system-error-functions.md#system_category).

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[value_type](#value_type)|Depolanan hata kodu değerini temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[default_error_condition](#default_error_condition)|Hata durumu nesnesi için hata kodu değerini depolar.|
|[değerinin](#equivalent)|Hata nesnelerinin eşdeğer olup olmadığını belirten bir değer döndürür.|
|[generic_category](#generic)||
|[message](#message)|Belirtilen hata kodunun adını döndürür.|
|[ada](#name)|Kategorinin adını döndürür.|
|[system_category](#system)||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_as)||
|[işleç = =](#op_eq_eq)|`error_category` nesneleri arasındaki eşitlik için sınar.|
|[operator!=](#op_neq)|`error_category` nesneleri arasındaki eşitsizlik için test eder.|
|[işleç <](#op_lt)|[Error_category](../standard-library/error-category-class.md) nesnenin karşılaştırma için geçirilen `error_category` nesnesinden küçük olup olmadığını sınar.|

## <a name="default_error_condition"></a><a name="default_error_condition"></a>default_error_condition

Hata durumu nesnesi için hata kodu değerini depolar.

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>Parametreler

*_Errval*\
[Error_condition](../standard-library/error-condition-class.md)depolanacak hata kodu değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(_Errval, *this)` döndürür.

### <a name="remarks"></a>Açıklamalar

### <a name="equivalent"></a><a name="equivalent"></a>değerinin

Hata nesnelerinin eşdeğer olup olmadığını belirten bir değer döndürür.

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

#### <a name="parameters"></a>Parametreler

*_Errval*\
Karşılaştırılacak hata kodu değeri.

*_Cond*\
Karşılaştırılacak [error_condition](../standard-library/error-condition-class.md) nesnesi.

*_Code*\
Karşılaştırılacak [error_code](../standard-library/error-code-class.md) nesnesi.

#### <a name="return-value"></a>Dönüş Değeri

Kategori ve değer eşitse **true** ; Aksi takdirde, **false**.

#### <a name="remarks"></a>Açıklamalar

İlk üye işlevi `*this == _Cond.category() && _Cond.value() == _Errval`döndürür.

İkinci üye işlevi `*this == _Code.category() && _Code.value() == _Errval`döndürür.

### <a name="generic_category"></a><a name="generic"></a>generic_category

```cpp
const error_category& generic_category();
```

### <a name="message"></a><a name="message"></a>İleti

Belirtilen hata kodunun adını döndürür.

```cpp
virtual string message(error_code::value_type val) const = 0;
```

#### <a name="parameters"></a>Parametreler

*val*\
Betimleyen hata kodu değeri.

#### <a name="return-value"></a>Dönüş Değeri

Kategorinin hata kodu *Val* ' nin açıklayıcı bir adını döndürür.

#### <a name="remarks"></a>Açıklamalar

### <a name="name"></a><a name="name"></a>ada

Kategorinin adını döndürür.

```cpp
virtual const char *name() const = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Kategorinin adını null sonlandırılmış bir bayt dizesi olarak döndürür.

### <a name="operator"></a><a name="op_as"></a>işleç =

```cpp
error_category& operator=(const error_category&) = delete;
```

### <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

`error_category` nesneleri arasındaki eşitlik için sınar.

```cpp
bool operator==(const error_category& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitlik için sınanacak nesne.

#### <a name="return-value"></a>Dönüş Değeri

nesneler eşitse **true** ; nesneler eşitse **false** .

#### <a name="remarks"></a>Açıklamalar

Bu üye işleci `this == &right`döndürür.

### <a name="operator"></a><a name="op_neq"></a>işleç! =

`error_category` nesneleri arasındaki eşitsizlik için test eder.

```cpp
bool operator!=(const error_category& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Eşitsizlik için test edilecek nesne.

#### <a name="return-value"></a>Dönüş Değeri

`error_category` nesnesi *sağda*geçirilen `error_category` nesneye eşit değilse **true** ; Aksi halde **yanlış**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci `(!*this == right)`döndürür.

### <a name="operatorlt"></a><a name="op_lt"></a>işleç&lt;

[Error_category](../standard-library/error-category-class.md) nesnenin karşılaştırma için geçirilen `error_category` nesnesinden küçük olup olmadığını sınar.

```cpp
bool operator<(const error_category& right) const;
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Karşılaştırılacak `error_category` nesnesi.

#### <a name="return-value"></a>Dönüş Değeri

`error_category` nesnesi karşılaştırma için geçirilen `error_category` nesneden küçükse **true** ; Aksi takdirde, **false**.

#### <a name="remarks"></a>Açıklamalar

Üye işleci `this < &right`döndürür.

### <a name="system_category"></a><a name="system"></a>system_category

```cpp
const error_category& system_category();
```

### <a name="value_type"></a><a name="value_type"></a>value_type

Depolanan hata kodu değerini temsil eden bir tür.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Açıklamalar

Bu tür tanımı **int**için bir eş anlamlı.

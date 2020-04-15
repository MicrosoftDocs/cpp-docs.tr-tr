---
title: Platform::Kutu Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: 7484bcda3f05a8a9e56a33222d0630d4597e1219
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354755"
---
# <a name="platformbox-class"></a>Platform::Kutu Sınıfı

Bir `Platform::Object` türde depolanacak `Windows::Foundation::DateTime` gibi bir değer türü `int` veya skaler bir tür sağlar. Genellikle açıkça kullanmak `Box` gerekli değildir, çünkü bir değer türünü . `Object^`

### <a name="syntax"></a>Sözdizimi

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>Gereksinimler

**Başlık:** vccorlib.h

**Ad alanı:** Platform

### <a name="members"></a>Üyeler

|Üye|Açıklama|
|------------|-----------------|
|[Box](#ctor) | `Box` Belirtilen türdeki bir değeri kapsülleyebilen bir oluşturur. |
|[operatör&lt;Kutusu const T&gt;^](#box-const-t) | Bir `const` `T` değer sınıfından veya `enum` sınıftan `T` `Box<T>`' a dönüştürmeleri kutulamayı sağlar. |
|[işleç&lt;Kutu const uçucu T&gt;^](#box-const-volatile-t) | `const volatile` Bir `T` değer sınıfından veya `enum` türünden `T` `Box<T>`kutulama dönüşümlerini ' n içine kadar etkinleştiriyor |
|[operatör&lt;Kutu T&gt;^](#box-t) | Bir değer sınıfından `T` `Box<T>`biri olan kutulama dönüşümlerini . |
|[işleç&lt;Kutu uçucu T&gt;^](#box-volatile-t) | `volatile` Bir `T` değer sınıfından veya `enum` türünden `T` `Box<T>`kutulama dönüşümlerini ' n içine kadar etkinleştiriyor |
|[Kutu::operatör T](#t) | Bir değer `T` sınıfından veya `enum` sınıftan `T` `Box<T>`' a dönüştürmeleri kutulamayı sağlar. |
|[Value özelliği](#value) | `Box` Nesnede kapsüllenen değeri verir. |

## <a name="boxbox-constructor"></a><a name="ctor"></a>Kutu::Kutu Oluşturucu

`Box` Belirtilen türdeki bir değeri kapsülleyebilen bir oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>Parametreler

*valueArg*<br/>
Kutulanacak değer `int`türü—örneğin, , , `bool` `float64`. `DateTime`

## <a name="boxoperator-boxltconst-tgt-operator"></a><a name="box-const-t"></a>Kutu::operatör&lt;Kutusu const T&gt;^ Operatör

Bir `const` `T` değer sınıfından veya `enum` sınıftan `T` `Box<T>`' a dönüştürmeleri kutulamayı sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir değer sınıfı, değer struct veya enum türü. [Varsayılan ad alanında](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Ref `Platform::Box<T>^` sınıfında kutulanan özgün değeri temsil eden bir örnek.

## <a name="boxoperator-boxltconst-volatile-tgt-operator"></a><a name="box-const-volatile-t"></a>Kutu::operatör&lt;Kutusu const&gt;uçucu T ^ Operatör

`const volatile` Bir `T` değer sınıfından veya `enum` türünden `T` `Box<T>`kutulama dönüşümlerini ' n içine kadar etkinleştiriyor

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir enum türü, değer sınıfı veya değer struct. [Varsayılan ad alanında](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Ref `Platform::Box<T>^` sınıfında kutulanan özgün değeri temsil eden bir örnek.

## <a name="boxoperator-boxlttgt-operator"></a><a name="box-t"></a>Kutu::operatör&lt;Kutusu&gt;T ^ Operatör

Bir değer sınıfından `T` `Box<T>`biri olan kutulama dönüşümlerini .

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir enum türü, değer sınıfı veya değer struct. [Varsayılan ad alanında](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Ref `Platform::Box<T>^` sınıfında kutulanan özgün değeri temsil eden bir örnek.

## <a name="boxoperator-boxltvolatile-tgt-operator"></a><a name="box-volatile-t"></a>Kutu::operatör&lt;Kutusu&gt;uçucu T ^ Operatör

`volatile` Bir `T` değer sınıfından veya `enum` türünden `T` `Box<T>`kutulama dönüşümlerini ' n içine kadar etkinleştiriyor

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir enum türü, değer sınıfı veya değer struct. [Varsayılan ad alanında](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Ref `Platform::Box<T>^` sınıfında kutulanan özgün değeri temsil eden bir örnek.

## <a name="boxoperator-t-operator"></a><a name="t"></a>Kutu::operatör T Operatörü

Bir değer `T` sınıfından veya `enum` sınıftan `T` `Box<T>`' a dönüştürmeleri kutulamayı sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir enum türü, değer sınıfı veya değer struct. [Varsayılan ad alanında](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

Ref `Platform::Box<T>^` sınıfında kutulanan özgün değeri temsil eden bir örnek.

## <a name="boxvalue-property"></a><a name="value"></a>Kutu::Değer Özelliği

`Box` Nesnede kapsüllenen değeri verir.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>Dönüş Değeri

Kutulanan değeri, kutulandırılmadan önce olduğu gibi aynı türde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Kutulama](../cppcx/boxing-c-cx.md)

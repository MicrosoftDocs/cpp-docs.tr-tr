---
description: 'Daha fazla bilgi edinin: Platform:: Box sınıfı'
title: 'Platform:: Box sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: cbfe8ec70f2ef4c58bf2c9459f2d0c4722817810
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284063"
---
# <a name="platformbox-class"></a>Platform:: Box sınıfı

Gibi bir değer türünün `Windows::Foundation::DateTime` veya türünde depolanması gibi skaler bir tür sağlar **`int`** `Platform::Object` . `Box`Bir değer türü aktardığınızda kutulama örtük olarak yapıldığından, genellikle açıkça kullanılması gerekli değildir `Object^` .

### <a name="syntax"></a>Syntax

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** vccorlib. h

**Ad alanı:** Platformunun

### <a name="members"></a>Üyeler

|Üye|Açıklama|
|------------|-----------------|
|[Box](#ctor) | `Box`Belirtilen türde bir değeri kapsüllemek için bir oluşturur. |
|[işleç kutusu &lt; const T&gt;^](#box-const-t) | **`const`** Değer sınıfı veya sınıfından paketleme dönüştürmelerini `T` sağlar **`enum`** `T` `Box<T>` . |
|[işleç kutusu &lt; const geçici T&gt;^](#box-const-volatile-t) | **`const volatile`** Değer sınıfından `T` veya **`enum`** türünden ' `T` ye paketleme dönüştürmelerini sağlar `Box<T>` . |
|[Operatör kutusu &lt; T&gt;^](#box-t) | Değer sınıfından paketleme dönüştürmelerini sağlar `T` `Box<T>` . |
|[Operatör kutusu &lt; geçici T&gt;^](#box-volatile-t) | **`volatile`** Değer sınıfından `T` veya **`enum`** türünden ' `T` ye paketleme dönüştürmelerini sağlar `Box<T>` . |
|[Box:: operator T](#t) | Değer sınıfı veya sınıfından paketleme dönüştürmelerini `T` sağlar **`enum`** `T` `Box<T>` . |
|[Value özelliği](#value) | Nesnede kapsüllenmiş değeri döndürür `Box` . |

## <a name="boxbox-constructor"></a><a name="ctor"></a> Box:: Box Oluşturucusu

`Box`Belirtilen türde bir değeri kapsüllemek için bir oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>Parametreler

*değer Kazang*<br/>
Kutulanmış değer türü — örneğin,,,, **`int`** **`bool`** `float64` `DateTime` .

## <a name="boxoperator-boxltconst-tgt-operator"></a><a name="box-const-t"></a> Box:: operator Box &lt; const T &gt; ^ işleci

**`const`** Değer sınıfı veya sınıfından paketleme dönüştürmelerini `T` sağlar **`enum`** `T` `Box<T>` .

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir değer sınıfı, değer yapısı veya sabit listesi türü. [Varsayılan ad alanındaki](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

`Platform::Box<T>^`Başvuru sınıfında kutulanmış özgün değeri temsil eden bir örnek.

## <a name="boxoperator-boxltconst-volatile-tgt-operator"></a><a name="box-const-volatile-t"></a> Box:: operator Box &lt; const geçici T &gt; ^ işleci

**`const volatile`** Değer sınıfından `T` veya **`enum`** türünden ' `T` ye paketleme dönüştürmelerini sağlar `Box<T>` .

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir numaralandırma türü, değer sınıfı veya değer yapısı. [Varsayılan ad alanındaki](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

`Platform::Box<T>^`Başvuru sınıfında kutulanmış özgün değeri temsil eden bir örnek.

## <a name="boxoperator-boxlttgt-operator"></a><a name="box-t"></a> Box:: operator Box &lt; T &gt; ^ işleci

Değer sınıfından paketleme dönüştürmelerini sağlar `T` `Box<T>` .

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir numaralandırma türü, değer sınıfı veya değer yapısı. [Varsayılan ad alanındaki](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

`Platform::Box<T>^`Başvuru sınıfında kutulanmış özgün değeri temsil eden bir örnek.

## <a name="boxoperator-boxltvolatile-tgt-operator"></a><a name="box-volatile-t"></a> Box:: operator kutusu &lt; geçici T &gt; ^ işleci

**`volatile`** Değer sınıfından `T` veya **`enum`** türünden ' `T` ye paketleme dönüştürmelerini sağlar `Box<T>` .

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir numaralandırma türü, değer sınıfı veya değer yapısı. [Varsayılan ad alanındaki](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

`Platform::Box<T>^`Başvuru sınıfında kutulanmış özgün değeri temsil eden bir örnek.

## <a name="boxoperator-t-operator"></a><a name="t"></a> Box:: operator T Işleci

Değer sınıfı veya sınıfından paketleme dönüştürmelerini `T` sağlar **`enum`** `T` `Box<T>` .

### <a name="syntax"></a>Sözdizimi

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Herhangi bir numaralandırma türü, değer sınıfı veya değer yapısı. [Varsayılan ad alanındaki](../cppcx/default-namespace.md)yerleşik türleri içerir.

### <a name="return-value"></a>Dönüş Değeri

`Platform::Box<T>^`Başvuru sınıfında kutulanmış özgün değeri temsil eden bir örnek.

## <a name="boxvalue-property"></a><a name="value"></a> Box:: Value özelliği

Nesnede kapsüllenmiş değeri döndürür `Box` .

### <a name="syntax"></a>Syntax

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>Dönüş Değeri

Kutulanmış değeri, ilk olarak paketlenmeden önce sahip olduğu aynı türde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)<br/>
[Kutulama](../cppcx/boxing-c-cx.md)

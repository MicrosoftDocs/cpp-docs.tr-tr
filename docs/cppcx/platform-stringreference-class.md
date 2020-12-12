---
description: 'Daha fazla bilgi edinin: Platform:: StringReference sınıfı'
title: 'Platform:: StringReference sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
ms.openlocfilehash: 5c211776bccbd3ba2fedaf769502f7dad71b6eb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307957"
---
# <a name="platformstringreference-class"></a>Platform:: StringReference sınıfı

`Platform::String^`Giriş parametrelerinden dize verilerini, en az kopyalama işlemlerine sahip diğer yöntemlere geçirmek için kullanabileceğiniz bir iyileştirme türü.

## <a name="syntax"></a>Syntax

```cpp
class StringReference
```

### <a name="remarks"></a>Açıklamalar

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[StringReference:: StringReference](#ctor)|Örnekleri oluşturmak için iki Oluşturucu `StringReference` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[StringReference::D ata](#data)|Dize verilerini Char16 değerlerinin bir dizisi olarak döndürür.|
|[StringReference:: length](#length)|Dizedeki karakter sayısını döndürür.|
|[StringReference:: GetHSTRING](#gethstring)|String verisini bir HSTRING olarak döndürür.|
|[StringReference:: GetString](#getstring)|Dize verilerini olarak döndürür `Platform::String^` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[StringReference:: operator =](#operator-assign)|Yeni bir `StringReference` örneğe bir atar `StringReference` .|
|[StringReference:: operator ()](#operator-call)|Bir `StringReference` öğesine dönüştürür `Platform::String^` .|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Üstbilgi:** vccorlib. h

## <a name="stringreferencedata-method"></a><a name="data"></a> StringReference::D ata yöntemi

Bunun içeriğini `StringReference` Char16 değerlerinin bir dizisi olarak döndürür.

### <a name="syntax"></a>Syntax

```cpp
const ::default::char16 * Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Char16 UNICODE metin karakterlerinden oluşan bir dizi.

## <a name="stringreferencegethstring-method"></a><a name="gethstring"></a> StringReference:: GetHSTRING yöntemi

Dizenin içeriğini bir olarak döndürür `__abi_HSTRING` .

### <a name="syntax"></a>Syntax

```cpp
__abi_HSTRING GetHSTRING() const;
```

### <a name="return-value"></a>Dönüş Değeri

`__abi_HSTRING`Dize verilerini içeren bir.

### <a name="remarks"></a>Açıklamalar

## <a name="stringreferencegetstring-method"></a><a name="getstring"></a> StringReference:: GetString yöntemi

Dizenin içeriğini bir olarak döndürür `Platform::String^` .

### <a name="syntax"></a>Syntax

```cpp
__declspec(no_release_return) __declspec(no_refcount)
    ::Platform::String^ GetString() const;
```

### <a name="return-value"></a>Dönüş Değeri

`Platform::String^`Dize verilerini içeren bir.

## <a name="stringreferencelength-method"></a><a name="length"></a> StringReference:: length yöntemi

Dizedeki karakter sayısını döndürür.

### <a name="syntax"></a>Syntax

```cpp
unsigned int Length() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakter sayısını belirten işaretsiz bir tamsayı.

### <a name="remarks"></a>Açıklamalar

## <a name="stringreferenceoperator-operator"></a><a name="operator-assign"></a> StringReference:: operator = Işleci

Belirtilen nesneyi geçerli `StringReference` nesneye atar.

### <a name="syntax"></a>Sözdizimi

```cpp
StringReference& operator=(const StringReference& __fstrArg);
StringReference& operator=(const ::default::char16* __strArg);
```

### <a name="parameters"></a>Parametreler

*__fstrArg*<br/>
`StringReference`Geçerli nesneyi başlatmak için kullanılan nesnenin adresi `StringReference` .

*__strArg*<br/>
Geçerli nesneyi başlatmak için kullanılan Char16 değerleri dizisine yönelik işaretçi `StringReference` .

### <a name="return-value"></a>Dönüş Değeri

Türündeki bir nesneye başvuru `StringReference` .

### <a name="remarks"></a>Açıklamalar

, `StringReference` Bir başvuru sınıfı değil, standart bir C++ sınıfı olduğundan **nesne tarayıcısı** görünmüyor.

## <a name="stringreferenceoperator--operator"></a><a name="operator-call"></a> StringReference:: operator () Işleci

Nesneyi `StringReference` `Platform::String^` nesnesine dönüştürür.

### <a name="syntax"></a>Syntax

```cpp
__declspec(no_release_return) __declspec(no_refcount)
         operator ::Platform::String^() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türündeki bir nesneye yönelik bir tanıtıcı `Platform::String` .

## <a name="stringreferencestringreference-constructor"></a><a name="ctor"></a> StringReference:: StringReference Oluşturucusu

`StringReference` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
StringReference();
StringReference(const StringReference& __fstrArg);
StringReference(const ::default::char16* __strArg);
StringReference(const ::default::char16* __strArg, size_t __lenArg);
```

### <a name="parameters"></a>Parametreler

*__fstrArg*<br/>
`StringReference`Verileri yeni örneği başlatmak için kullanılır.

*__strArg*<br/>
Yeni örneği başlatmak için kullanılan Char16 değerleri dizisine yönelik işaretçi.

*__lenArg*<br/>
İçindeki öğe sayısı `__strArg` .

### <a name="remarks"></a>Açıklamalar

Bu oluşturucunun ilk sürümü varsayılan oluşturucudur. İkinci sürüm, `StringReference` parametresi tarafından belirtilen nesneden yeni bir örnek sınıfı başlatır `__fstrArg` . Üçüncü ve dördüncü aşırı yüklemeler, `StringReference` Char16 değerlerinin dizisinden yeni bir örnek başlatır. Char16 16 bit UNICODE metin karakterini temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[Platform:: StringReference sınıfı](../cppcx/platform-stringreference-class.md)

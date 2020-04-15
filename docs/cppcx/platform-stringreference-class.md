---
title: Platform::StringReference Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
ms.openlocfilehash: 4748eecdf67ae5a60ddf97783a934a05e80b406c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374655"
---
# <a name="platformstringreference-class"></a>Platform::StringReference Sınıfı

En az kopyalama işlemleriyle giriş parametrelerinden `Platform::String^` diğer yöntemlere string verilerini geçirmek için kullanabileceğiniz bir enoptimizasyon türü.

## <a name="syntax"></a>Sözdizimi

```cpp
class StringReference
```

### <a name="remarks"></a>Açıklamalar

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[StringReference::StringReference](#ctor)|Örnekleri oluşturmak için iki `StringReference`oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[StringReference::Data](#data)|Dize verilerini char16 değerleri dizisi olarak döndürür.|
|[StringReference::Uzunluk](#length)|Dizedeki karakter sayısını döndürür.|
|[StringReference::GetHSTRING](#gethstring)|Dize verilerini HSTRING olarak döndürür.|
|[StringReference::GetString](#getstring)|Dize verilerini `Platform::String^`' olarak döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[StringReference::operator=](#operator-assign)|Yeni `StringReference` bir `StringReference` örneğe aatar.|
|[StringReference::operator()](#operator-call)|A'yı `StringReference` bir'e `Platform::String^`dönüştürür.|

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Başlık:** vccorlib.h

## <a name="stringreferencedata-method"></a><a name="data"></a>StringReference::Data Yöntemi

Bunun `StringReference` içeriğini char16 değerleri dizisi olarak döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
const ::default::char16 * Data() const;
```

### <a name="return-value"></a>Dönüş Değeri

Char16 UNICODE metin karakterleri dizisi.

## <a name="stringreferencegethstring-method"></a><a name="gethstring"></a>StringReference::GetHSTRING Yöntemi

Dize içeriğini bir `__abi_HSTRING`.

### <a name="syntax"></a>Sözdizimi

```cpp
__abi_HSTRING GetHSTRING() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize `__abi_HSTRING` verilerini içeren bir.

### <a name="remarks"></a>Açıklamalar

## <a name="stringreferencegetstring-method"></a><a name="getstring"></a>StringReference::GetString Yöntemi

Dize içeriğini bir `Platform::String^`. olarak döndürür

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(no_release_return) __declspec(no_refcount)
    ::Platform::String^ GetString() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize verilerini içeren a. `Platform::String^`

## <a name="stringreferencelength-method"></a><a name="length"></a>StringReference::Uzunluk Yöntemi

Dizedeki karakter sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int Length() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizedeki karakter sayısını belirten imzasız bir karşıcı.

### <a name="remarks"></a>Açıklamalar

## <a name="stringreferenceoperator-operator"></a><a name="operator-assign"></a>StringReference::operator= Operatör

Belirtilen nesneyi geçerli `StringReference` nesneye atar.

### <a name="syntax"></a>Sözdizimi

```cpp
StringReference& operator=(const StringReference& __fstrArg);
StringReference& operator=(const ::default::char16* __strArg);
```

### <a name="parameters"></a>Parametreler

*__fstrArg*<br/>
Geçerli `StringReference` nesneyi `StringReference` başlatmak için kullanılan bir nesnenin adresi.

*__strArg*<br/>
Geçerli `StringReference` nesneyi başlatmak için kullanılan char16 değerleri dizisini işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Türdeki `StringReference`bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Ref `StringReference` sınıfı değil standart bir C++ sınıfı olduğundan Object **Browser'da**görünmez.

## <a name="stringreferenceoperator--operator"></a><a name="operator-call"></a>StringReference::operator() Operatör

Nesneyi `StringReference` nesneye `Platform::String^` dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(no_release_return) __declspec(no_refcount)
         operator ::Platform::String^() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türdeki `Platform::String`bir nesneye bir tanıtıcı.

## <a name="stringreferencestringreference-constructor"></a><a name="ctor"></a>StringReference::StringReference Constructor

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
Verileri `StringReference` yeni örneği başlatmak için kullanılır.

*__strArg*<br/>
Yeni örneği başlatmak için kullanılan char16 değerleri dizisiiçin işaretçi.

*__lenArg*<br/>
'deki `__strArg`öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucunun ilk sürümü varsayılan oluşturucudur. İkinci `__fstrArg` sürüm, parametre `StringReference` tarafından belirtilen nesneden yeni bir örnek sınıf ını başolarak adlandırır. Üçüncü ve dördüncü aşırı yüklemeler `StringReference` char16 değerlerinden bir dizi yeni bir örneği başlatma. char16 16 bit UNICODE metin karakterini temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[Platform::StringReference Sınıfı](../cppcx/platform-stringreference-class.md)

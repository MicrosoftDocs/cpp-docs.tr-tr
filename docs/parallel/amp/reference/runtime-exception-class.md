---
title: runtime_exception Sınıfı
ms.date: 03/27/2019
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: ff54357055d373db98f469b071edc75fce75e0b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336790"
---
# <a name="runtime_exception-class"></a>runtime_exception Sınıfı

C++ Hızlandırılmış Kütleparalelliği (AMP) kitaplığındaki özel durumlar için temel tür.

### <a name="syntax"></a>Sözdizimi

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[runtime_exception Yapıcı](#ctor)|`runtime_exception` sınıfının yeni bir örneğini başlatır.|
|[~runtime_exception Yıkıcı](#dtor)|Nesneyi `runtime_exception` yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get_error_code](#get_error_code)|Özel durum neden hata kodunu döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işleç=](#operator_eq)|Belirtilen `runtime_exception` nesnenin içeriğini buna kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt.h

**Ad alanı:** Eşzamanlılık

## <a name="runtime_exception-constructor"></a><a name="ctor"></a>runtime_exception Yapıcı

Sınıfın yeni bir örneğini başolarak adlandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Özel durum neden hata açıklaması.

*_Hresult*<br/>
Özel durum neden hata HRESULT.

*_Other*<br/>
Kopyalanması `runtime_exception` gereken nesne.

### <a name="return-value"></a>Dönüş Değeri

`runtime_exception` nesnesi.

## <a name="runtime_exception-destructor"></a><a name="dtor"></a>~runtime_exception Yıkıcı

Nesneyi yok eder.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a><a name="get_error_code"></a>get_error_code

Özel durum neden hata kodunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Özel durum neden hata HRESULT.

## <a name="operator"></a><a name="operator_eq"></a>işleç=

Belirtilen `runtime_exception` nesnenin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanması `runtime_exception` gereken nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu `runtime_exception` nesneye bir başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)

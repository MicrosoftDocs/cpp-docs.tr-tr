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
ms.openlocfilehash: 6ad784720833d2ae5de7d653d132ba144aec2677
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126389"
---
# <a name="runtime_exception-class"></a>runtime_exception Sınıfı

C++ Hızlandırılmış çok büyük paralellik (amp) kitaplığındaki özel durumların temel türü.

### <a name="syntax"></a>Sözdizimi

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[runtime_exception Oluşturucusu](#ctor)|`runtime_exception` sınıfının yeni bir örneğini başlatır.|
|[~ runtime_exception yok edici](#dtor)|`runtime_exception` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_error_code](#get_error_code)|Özel duruma neden olan hata kodunu döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Belirtilen `runtime_exception` nesnesinin içeriğini buna kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="ctor"></a>runtime_exception Oluşturucusu

Sınıfının yeni bir örneğini başlatır.

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
Özel duruma neden olan hatanın açıklaması.

*_Hresult*<br/>
Özel duruma neden olan hata HRESULT.

*_Other*<br/>
Kopyalanacak `runtime_exception` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`runtime_exception` nesnesi.

## <a name="dtor"></a>~ runtime_exception yok edici

Nesneyi yok eder.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a>get_error_code

Özel duruma neden olan hata kodunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Özel duruma neden olan hata HRESULT.

## <a name="operator_eq"></a>işleç =
  Belirtilen `runtime_exception` nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanacak `runtime_exception` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `runtime_exception` nesnesine bir başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)

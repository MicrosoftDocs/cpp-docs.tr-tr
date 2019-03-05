---
title: runtime_exception Sınıfı
ms.date: 11/04/2016
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: 5260d2f1d2e5a6a6498d501599037a90bc7bc9a0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289669"
---
# <a name="runtimeexception-class"></a>runtime_exception Sınıfı

C++ hızlandırılmış yoğun paralellik (AMP) Kitaplığı'nda özel durumlar için temel türü.

### <a name="syntax"></a>Sözdizimi

```
class runtime_exception : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[runtime_exception Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `runtime_exception` sınıfı.|
|[~ runtime_exception yok Edicisi](#dtor)|Yok eder `runtime_exception` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_error_code](#runtime_exception__get_error_code)|Özel duruma neden oldu hata kodu döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `runtime_exception` bu nesne içine.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** Eşzamanlılık

## <a name="runtime_exception__ctor"></a>  runtime_exception Oluşturucusu

Sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Özel duruma neden olan hata açıklaması.

*_Hresult*<br/>
Özel duruma neden olan hatanın HRESULT.

*_Diğer*<br/>
`runtime_exception` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

`runtime_exception` Nesne.

## <a name="dtor"></a>  ~ runtime_exception yok Edicisi

Nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```
virtual ~runtime_exception() throw();
```

## <a name="runtime_exception__get_error_code"></a>  get_error_code

Özel duruma neden oldu hata kodu döndürür.

### <a name="syntax"></a>Sözdizimi

```
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Özel duruma neden olan hatanın HRESULT.

## <a name="runtime_exception__operator_eq"></a>  işleç =
  Belirtilen içeriğini kopyalar `runtime_exception` bu nesne içine.

### <a name="syntax"></a>Sözdizimi

```
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`runtime_exception` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `runtime_exception` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)

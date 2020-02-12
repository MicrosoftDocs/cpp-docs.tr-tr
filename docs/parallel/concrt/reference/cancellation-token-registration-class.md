---
title: cancellation_token_registration Sınıfı
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: 9342841e207c93b66521c2fc742c1b1114682f78
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142247"
---
# <a name="cancellation_token_registration-class"></a>cancellation_token_registration Sınıfı

`cancellation_token_registration` sınıfı, bir `cancellation_token`geri çağırma bildirimini temsil eder. Bir `cancellation_token` `register` yöntemi iptal gerçekleştiğinde bildirim almak için kullanıldığında, çağıranın `deregister` yönteminin kullanımı ile belirli bir geri çağırma işlemini istemesi için geri çağırmada tanıtıcı olarak bir `cancellation_token_registration` nesnesi döndürülür.

## <a name="syntax"></a>Sözdizimi

```cpp
class cancellation_token_registration;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~ cancellation_token_registration yok edici](#dtor)||

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[işleç =](#operator_eq)||
|[işleç = =](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`cancellation_token_registration`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** pplcancellation_token. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ cancellation_token_registration

```cpp
~cancellation_token_registration();
```

## <a name="ctor"></a>cancellation_token_registration

```cpp
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Kopyalanacak veya taşınacak `cancellation_token_registration`.

## <a name="operator_neq"></a>işleç! =

```cpp
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak `cancellation_token_registration`.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator_eq"></a>işleç =

```cpp
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Atanacak `cancellation_token_registration`.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator_eq_eq"></a>işleç = =

```cpp
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Karşılaştırılacak `cancellation_token_registration`.

### <a name="return-value"></a>Dönüş Değeri

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

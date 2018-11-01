---
title: invalid_compute_domain Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 264b93d11b82eb00ac85e92413ca1a7071e06879
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582253"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain Sınıfı

Çalışma zamanı sırasında belirtilen hesaplama alanını kullanarak bir çekirdeği başlatamadığında oluşturulan özel durum [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) çağrı sitesini.

## <a name="syntax"></a>Sözdizimi

```
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_compute_domain Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `invalid_compute_domain` sınıfı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** eşzamanlılık

## <a name="ctor"></a> invalid_compute_domain

Sınıfının yeni bir örneğini başlatır.

## <a name="syntax"></a>Sözdizimi

```
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

Örneği `invalid_compute_domain` sınıfı

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)

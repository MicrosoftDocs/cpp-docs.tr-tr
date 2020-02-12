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
ms.openlocfilehash: 3b8179e8e92665fa6482bd092504af71aa0106f0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126467"
---
# <a name="invalid_compute_domain-class"></a>invalid_compute_domain Sınıfı

Çalışma zamanı [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) çağrı sitesinde belirtilen işlem etki alanını kullanarak bir çekirdek başlatamadığınızda oluşturulan özel durum.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_compute_domain Oluşturucusu](#ctor)|`invalid_compute_domain` sınıfının yeni bir örneğini başlatır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="ctor"></a>invalid_compute_domain

Sınıfının yeni bir örneğini başlatır.

## <a name="syntax"></a>Sözdizimi

```cpp
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklaması.

### <a name="return-value"></a>Dönüş Değeri

`invalid_compute_domain` sınıfının bir örneği

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)

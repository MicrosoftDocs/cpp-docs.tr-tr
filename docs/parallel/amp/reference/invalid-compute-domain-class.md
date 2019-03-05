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
ms.openlocfilehash: 51fcd9e42bc4497131da5adb3dff72efb46537b3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296884"
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

**Namespace:** Eşzamanlılık

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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)

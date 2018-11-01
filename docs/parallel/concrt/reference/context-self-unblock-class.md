---
title: context_self_unblock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
helpviewer_keywords:
- context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
ms.openlocfilehash: 5cb7fc951a4c62f4d299ce7d394e9f8268d7ed74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622176"
---
# <a name="contextselfunblock-class"></a>context_self_unblock Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır `Unblock` yöntemi bir `Context` nesnesi aynı bağlamdan çağrılır. Bu tarafından belirtilen bir bağlamda kendisini engelini kaldırmak için girişiminde bulunulduğunu.

## <a name="syntax"></a>Sözdizimi

```
class context_self_unblock : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[context_self_unblock](#ctor)|Fazla Yüklendi. Oluşturur bir `context_self_unblock` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`context_self_unblock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> context_self_unblock

Oluşturur bir `context_self_unblock` nesne.

```
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

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
ms.openlocfilehash: 900dc68eac4441bd1db3818d3c1f30698b80a6e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296182"
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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

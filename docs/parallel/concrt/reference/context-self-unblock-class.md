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
ms.openlocfilehash: 883d5630251a6ea13afba1164f221a0da1773c17
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143106"
---
# <a name="context_self_unblock-class"></a>context_self_unblock Sınıfı

Bu sınıf, bir `Context` nesnesinin `Unblock` yöntemi aynı içerikten çağrıldığında oluşturulan bir özel durumu açıklar. Bu, belirli bir bağlam tarafından onun engellemesini kaldırmak için bir girişim olduğunu gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
class context_self_unblock : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[context_self_unblock](#ctor)|Fazla Yüklendi. `context_self_unblock` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`context_self_unblock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>context_self_unblock

`context_self_unblock` nesnesi oluşturur.

```cpp
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

---
title: invalid_oversubscribe_operation Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 7a879fc2da2f963cd4b5ea5fcd7e9506f86ce051
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140840"
---
# <a name="invalid_oversubscribe_operation-class"></a>invalid_oversubscribe_operation Sınıfı

Bu sınıf, `Context::Oversubscribe` yöntemi, `_BeginOversubscription` parametresi **true**olarak ayarlanmış `Context::Oversubscribe` yöntemine önceki bir çağrı olmadan, `_BeginOversubscription` parametresi **false** olarak çağrıldığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Fazla Yüklendi. `invalid_oversubscribe_operation` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>invalid_oversubscribe_operation

`invalid_oversubscribe_operation` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

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
ms.openlocfilehash: 200743d41c1c45f2a957dba0716dd7aa07e3de76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405319"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır `Context::Oversubscribe` yöntemi çağrıldığında `_BeginOversubscription` parametresini **false** çağrıda olmadan `Context::Oversubscribe` yöntemiyle `_BeginOversubscription` parametre kümesi için **true**.

## <a name="syntax"></a>Sözdizimi

```
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_oversubscribe_operation` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> invalid_oversubscribe_operation

Oluşturur bir `invalid_oversubscribe_operation` nesne.

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

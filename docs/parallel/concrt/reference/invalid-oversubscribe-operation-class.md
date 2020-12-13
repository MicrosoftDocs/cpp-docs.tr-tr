---
description: 'Hakkında daha fazla bilgi edinin: invalid_oversubscribe_operation sınıfı'
title: invalid_oversubscribe_operation Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 435e3ce0eba29188711c51aa9253060fc08ac62c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334526"
---
# <a name="invalid_oversubscribe_operation-class"></a>invalid_oversubscribe_operation Sınıfı

Bu sınıf, `Context::Oversubscribe` yöntemi parametresi `_BeginOversubscription` **`false`** `Context::Oversubscribe` olarak ayarlanmış bir yönteme önceki bir çağrı olmadan olarak `_BeginOversubscription` çağrıldığında oluşturulan **`true`** bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Fazla Yüklendi. Bir `invalid_oversubscribe_operation` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_oversubscribe_operation"></a><a name="ctor"></a> invalid_oversubscribe_operation

Bir `invalid_oversubscribe_operation` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)

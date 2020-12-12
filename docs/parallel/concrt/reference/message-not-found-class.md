---
description: 'Hakkında daha fazla bilgi edinin: message_not_found sınıfı'
title: message_not_found Sınıfı
ms.date: 11/04/2016
f1_keywords:
- message_not_found
- CONCRT/concurrency::message_not_found
- CONCRT/concurrency::message_not_found::message_not_found
helpviewer_keywords:
- message_not_found class
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
ms.openlocfilehash: c0b098a530768617b2fa2cf52dfe374dc44a2c12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169391"
---
# <a name="message_not_found-class"></a>message_not_found Sınıfı

Bu sınıf, bir ileti bloğu istenen iletiyi bulamadığında oluşan bir özel durum tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class message_not_found : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[message_not_found](#ctor)|Fazla Yüklendi. Bir `message_not_found` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`message_not_found`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="message_not_found"></a><a name="ctor"></a> message_not_found

Bir `message_not_found` nesnesi oluşturur.

```cpp
explicit _CRTIMP message_not_found(_In_z_ const char* _Message) throw();

message_not_found() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md)

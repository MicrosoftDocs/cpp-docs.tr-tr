---
description: 'Hakkında daha fazla bilgi edinin: improper_scheduler_attach sınıfı'
title: improper_scheduler_attach Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
helpviewer_keywords:
- improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
ms.openlocfilehash: 755cd72d20eb88dbd1ff7c58586f0aaf3b964a6a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334626"
---
# <a name="improper_scheduler_attach-class"></a>improper_scheduler_attach Sınıfı

Bu sınıf, `Attach` yöntemi `Scheduler` zaten geçerli bağlama eklenmiş bir nesne üzerinde çağrıldığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|Fazla Yüklendi. Bir `improper_scheduler_attach` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="improper_scheduler_attach"></a><a name="ctor"></a> improper_scheduler_attach

Bir `improper_scheduler_attach` nesnesi oluşturur.

```cpp
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)

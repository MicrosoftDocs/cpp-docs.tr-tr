---
description: 'Hakkında daha fazla bilgi edinin: default_scheduler_exists sınıfı'
title: default_scheduler_exists Sınıfı
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 6921f7bd820271cf590707c2e56cefa9f576cefe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284856"
---
# <a name="default_scheduler_exists-class"></a>default_scheduler_exists Sınıfı

Bu sınıf, `Scheduler::SetDefaultSchedulerPolicy` işlem içinde varsayılan bir Zamanlayıcı zaten varken yöntemi çağrıldığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|Fazla Yüklendi. Bir `default_scheduler_exists` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="default_scheduler_exists"></a><a name="ctor"></a> default_scheduler_exists

Bir `default_scheduler_exists` nesnesi oluşturur.

```cpp
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)

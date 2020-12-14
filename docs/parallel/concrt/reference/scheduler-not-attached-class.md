---
description: 'Hakkında daha fazla bilgi edinin: scheduler_not_attached sınıfı'
title: scheduler_not_attached Sınıfı
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: 1d412ffecea288d4ecad1d0c2949e7444adfd913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188865"
---
# <a name="scheduler_not_attached-class"></a>scheduler_not_attached Sınıfı

Bu sınıf, bir Scheduler 'ın geçerli içeriğe eklenmesini gerektiren bir işlem gerçekleştirildiğinde oluşan bir özel durum tanımlar ve biri değildir.

## <a name="syntax"></a>Syntax

```cpp
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Fazla Yüklendi. Bir `scheduler_not_attached` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="scheduler_not_attached"></a><a name="ctor"></a> scheduler_not_attached

Bir `scheduler_not_attached` nesnesi oluşturur.

```cpp
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)

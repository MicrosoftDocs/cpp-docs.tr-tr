---
title: scheduler_not_attached Sınıfı
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: a3b1c113e5c6c5feb5b2fa1940ee9b984233e4af
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142203"
---
# <a name="scheduler_not_attached-class"></a>scheduler_not_attached Sınıfı

Bu sınıf, bir Scheduler 'ın geçerli içeriğe eklenmesini gerektiren bir işlem gerçekleştirildiğinde oluşan bir özel durum tanımlar ve biri değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Fazla Yüklendi. `scheduler_not_attached` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>scheduler_not_attached

`scheduler_not_attached` nesnesi oluşturur.

```cpp
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)

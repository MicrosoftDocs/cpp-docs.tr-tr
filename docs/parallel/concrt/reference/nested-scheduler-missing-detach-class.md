---
description: 'Hakkında daha fazla bilgi edinin: nested_scheduler_missing_detach sınıfı'
title: nested_scheduler_missing_detach Sınıfı
ms.date: 11/04/2016
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
ms.openlocfilehash: 3d1232b8f9b807835f5b4b1e19c6049d049f12f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202112"
---
# <a name="nested_scheduler_missing_detach-class"></a>nested_scheduler_missing_detach Sınıfı

Bu sınıf, Eşzamanlılık Çalışma Zamanı bir özel durum tanımlar ve bu, `CurrentScheduler::Detach` yöntemi, nesne yöntemi kullanılarak ikinci bir Scheduler 'a eklenmiş bir bağlamda yöntemi çağırmak için ihmal ettiğiniz algılandığında oluşur `Attach` `Scheduler` .

## <a name="syntax"></a>Syntax

```cpp
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Fazla Yüklendi. Bir `nested_scheduler_missing_detach` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu özel durum yalnızca, `Attach` `Scheduler` zaten başka bir Scheduler 'a ait olan veya başka bir zamanlayıcıya bağlanmış bir bağlamda bir nesnenin yöntemini çağırarak bir zamanlayıcıyı bir tane iç içe aktardığınızda oluşturulur. Eşzamanlılık Çalışma Zamanı, sorunu bulmaya yardımcı olması için senaryoyu algılayabildiği zaman bu özel durumu mümkün olduğunda oluşturur. Yöntemi çağırmak için her denenmemesi örneğinin değil, `CurrentScheduler::Detach` Bu özel durumu oluşturmak için garanti edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="nested_scheduler_missing_detach"></a><a name="ctor"></a> nested_scheduler_missing_detach

Bir `nested_scheduler_missing_detach` nesnesi oluşturur.

```cpp
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)

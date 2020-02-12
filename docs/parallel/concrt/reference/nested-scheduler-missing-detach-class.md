---
title: nested_scheduler_missing_detach Sınıfı
ms.date: 11/04/2016
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
ms.openlocfilehash: 8c9553b036890c4ce28f1060bfe2f58ee1904935
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138862"
---
# <a name="nested_scheduler_missing_detach-class"></a>nested_scheduler_missing_detach Sınıfı

Bu sınıf, Eşzamanlılık Çalışma Zamanı bir özel durum tanımlar ve bu, `Scheduler` nesnesinin `Attach` yöntemini kullanarak ikinci bir Scheduler 'a eklenmiş bir bağlamda `CurrentScheduler::Detach` yöntemini çağırmak için ihmal edileceğini algıladığında oluşur.

## <a name="syntax"></a>Sözdizimi

```cpp
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Fazla Yüklendi. `nested_scheduler_missing_detach` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu özel durum yalnızca, zaten başka bir Scheduler 'a ait olan veya başka bir zamanlayıcıya bağlanmış bir bağlamda bir `Scheduler` nesnesinin `Attach` yöntemini çağırarak bir zamanlayıcıyı bir başka iç içe aktardığınızda oluşturulur. Eşzamanlılık Çalışma Zamanı, sorunu bulmaya yardımcı olması için senaryoyu algılayabildiği zaman bu özel durumu mümkün olduğunda oluşturur. `CurrentScheduler::Detach` yöntemini çağırmak için her denenmemesi örneği değil, bu özel durumu oluşturmak için garanti edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>nested_scheduler_missing_detach

`nested_scheduler_missing_detach` nesnesi oluşturur.

```cpp
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)

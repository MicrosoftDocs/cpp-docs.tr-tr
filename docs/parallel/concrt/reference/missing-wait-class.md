---
title: missing_wait Sınıfı
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: cf81d1ee6c144da210da5b1f37aca7910ae37bc8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142384"
---
# <a name="missing_wait-class"></a>missing_wait Sınıfı

Bu sınıf, nesnenin yıkıcının yürütüldüğü sırada bir `task_group` veya `structured_task_group` nesnesine hala zamanlanan görevler olduğunda oluşturulan bir özel durumu açıklar. Bu özel durum, bir özel durumun sonucu olarak bir yığın geri sarma işlemi nedeniyle yok edici olursa hiçbir durum oluşturulmaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class missing_wait : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[missing_wait](#ctor)|Fazla Yüklendi. `missing_wait` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Özel durum akışı yok, bu nesnenin Destruct 'a izin vermeden önce bir `task_group` veya `structured_task_group` nesnesinin `wait` ya da `run_and_wait` yöntemini çağırmak sizin sorumluluğunuzdadır. Çalışma zamanı, `wait` veya `run_and_wait` yöntemini çağırmayı unuttuistediğinizi belirten bir gösterge olarak bu özel durumu oluşturur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`missing_wait`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>missing_wait

`missing_wait` nesnesi oluşturur.

```cpp
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[bekleneceğini](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)

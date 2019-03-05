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
ms.openlocfilehash: 68d24d710eec4fd602e64cc3cbde810db2b1a495
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297651"
---
# <a name="missingwait-class"></a>missing_wait Sınıfı

Bu sınıf için yine de zamanlanmış görevler olduğunda oluşturulan bir özel açıklayan bir `task_group` veya `structured_task_group` sırada bu nesnenin nesne yok Edicisi yürütür. Bu özel durumun hiçbir zaman yok edici bir özel durum sonucu olarak geriye doğru izleme yığın nedeniyle ulaşılırsa oluşturulur.

## <a name="syntax"></a>Sözdizimi

```
class missing_wait : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[missing_wait](#ctor)|Fazla Yüklendi. Oluşturur bir `missing_wait` nesne.|

## <a name="remarks"></a>Açıklamalar

Özel durum akış ya da çağırmak için sorumlu `wait` veya `run_and_wait` yöntemi bir `task_group` veya `structured_task_group` söz konusu nesneyi yok etmek üzere izin vermeden önce nesne. Çalışma zamanı bu Exception'a çağrılacak unuttum bir gösterge olarak `wait` veya `run_and_wait` yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`missing_wait`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> missing_wait

Oluşturur bir `missing_wait` nesne.

```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[bekleme](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)

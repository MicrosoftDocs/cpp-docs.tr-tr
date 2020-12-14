---
description: 'Hakkında daha fazla bilgi edinin: missing_wait sınıfı'
title: missing_wait Sınıfı
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: bfbfdf4c2a52573d08c048bac278386aed1dc5a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202190"
---
# <a name="missing_wait-class"></a>missing_wait Sınıfı

Bu sınıf `task_group` `structured_task_group` , nesnenin yıkıcının yürütüldüğü sırada bir veya nesnesine hala zamanlanan görevler olduğunda oluşturulan bir özel durumu açıklar. Bu özel durum, bir özel durumun sonucu olarak bir yığın geri sarma işlemi nedeniyle yok edici olursa hiçbir durum oluşturulmaz.

## <a name="syntax"></a>Syntax

```cpp
class missing_wait : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[missing_wait](#ctor)|Fazla Yüklendi. Bir `missing_wait` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Özel durum akışı yok, `wait` `run_and_wait` `task_group` `structured_task_group` Bu nesnenin Destruct kullanmasına izin vermeden önce bir veya nesnesinin ya da yöntemini çağırmak sizin sorumluluğunuzdadır. Çalışma zamanı, veya yöntemini çağırmayı unuttubir gösterge olarak bu özel durumu `wait` oluşturur `run_and_wait` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`missing_wait`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="missing_wait"></a><a name="ctor"></a> missing_wait

Bir `missing_wait` nesnesi oluşturur.

```cpp
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[task_group sınıfı](task-group-class.md)<br/>
[bekleneceğini](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group sınıfı](structured-task-group-class.md)

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
ms.openlocfilehash: be8a04c7cf6ef5aa4d6070e92df14e643395ef00
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262271"
---
# <a name="schedulernotattached-class"></a>scheduler_not_attached Sınıfı

Bu sınıf, bir işlem için geçerli bağlam eklenmesi bir zamanlayıcı gerektiren gerçekleştirilir ve bulunmaması olduğunda oluşturulan bir özel durum açıklar.

## <a name="syntax"></a>Sözdizimi

```
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Fazla Yüklendi. Oluşturur bir `scheduler_not_attached` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> scheduler_not_attached

Oluşturur bir `scheduler_not_attached` nesne.

```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)

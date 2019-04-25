---
title: invalid_link_target Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: 3ef34ab7607c444044b6dde17f3db3f73d0d7086
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205662"
---
# <a name="invalidlinktarget-class"></a>invalid_link_target Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır `link_target` ileti bloğunun yöntemi çağrılır ve ileti bloğu Hedefe bağlanamıyor. Bu ileti bloğu izin verilen bağlantı sayısını aşan veya iki kez aynı kaynak için belirli bir hedef bağlantı girişimi sonucu olabilir.

## <a name="syntax"></a>Sözdizimi

```
class invalid_link_target : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_link_target](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_link_target` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_link_target`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> invalid_link_target

Oluşturur bir `invalid_link_target` nesne.

```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)

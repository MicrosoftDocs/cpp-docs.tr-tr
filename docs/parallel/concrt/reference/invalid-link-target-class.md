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
ms.openlocfilehash: bd3d82c06c174c69c60dec33592110f4de72ac99
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141044"
---
# <a name="invalid_link_target-class"></a>invalid_link_target Sınıfı

Bu sınıf, bir mesajlaşma bloğunun `link_target` yöntemi çağrıldığında ve mesajlaşma bloğu hedefle bağlantı kuramıyor durumunda oluşturulan bir özel durumu açıklar. Bu, mesajlaşma bloğunun izin verdiği bağlantı sayısını aşmanın veya belirli bir hedefin aynı kaynağa iki kez bağlantı kurmaya çalıştığı sonuç olabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_link_target : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_link_target](#ctor)|Fazla Yüklendi. `invalid_link_target` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_link_target`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>invalid_link_target

`invalid_link_target` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)

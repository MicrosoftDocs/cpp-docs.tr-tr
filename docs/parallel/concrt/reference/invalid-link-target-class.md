---
description: 'Hakkında daha fazla bilgi edinin: invalid_link_target sınıfı'
title: invalid_link_target Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: d080886c3aab0ecc120d4ce13f5f75f2eecfea8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334583"
---
# <a name="invalid_link_target-class"></a>invalid_link_target Sınıfı

Bu sınıf, `link_target` bir mesajlaşma bloğunun yöntemi çağrıldığında ve mesajlaşma bloğu hedefle bağlantı kuramadı durumunda oluşturulan bir özel durumu açıklar. Bu, mesajlaşma bloğunun izin verdiği bağlantı sayısını aşmanın veya belirli bir hedefin aynı kaynağa iki kez bağlantı kurmaya çalıştığı sonuç olabilir.

## <a name="syntax"></a>Syntax

```cpp
class invalid_link_target : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_link_target](#ctor)|Fazla Yüklendi. Bir `invalid_link_target` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_link_target`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_link_target"></a><a name="ctor"></a> invalid_link_target

Bir `invalid_link_target` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md)

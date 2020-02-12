---
title: improper_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
ms.openlocfilehash: 886444f3e856234be010715a8ee0c707cf919bb4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142393"
---
# <a name="improper_lock-class"></a>improper_lock Sınıfı

Bu sınıf, bir kilit yanlış edinildiği zaman oluşturulan bir özel durum tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class improper_lock : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_lock](#ctor)|Fazla Yüklendi. Bir `improper_lock exception`oluşturur.|

## <a name="remarks"></a>Açıklamalar

Genellikle, bu özel durum, yinelemeli olmayan bir kilidi aynı bağlamda yinelemeli olarak almak için bir girişim yapıldığında oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_lock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>improper_lock

Bir `improper_lock exception`oluşturur.

```cpp
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[critical_section Sınıfı](critical-section-class.md)<br/>
[reader_writer_lock Sınıfı](reader-writer-lock-class.md)

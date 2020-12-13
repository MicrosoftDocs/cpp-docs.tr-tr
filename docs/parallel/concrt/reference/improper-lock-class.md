---
description: 'Hakkında daha fazla bilgi edinin: improper_lock sınıfı'
title: improper_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
ms.openlocfilehash: 8e29172ad171bbd3f95b3079840fb50b91dfe577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334639"
---
# <a name="improper_lock-class"></a>improper_lock Sınıfı

Bu sınıf, bir kilit yanlış edinildiği zaman oluşturulan bir özel durum tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class improper_lock : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_lock](#ctor)|Fazla Yüklendi. Oluşturur `improper_lock exception` .|

## <a name="remarks"></a>Açıklamalar

Genellikle, bu özel durum, yinelemeli olmayan bir kilidi aynı bağlamda yinelemeli olarak almak için bir girişim yapıldığında oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_lock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="improper_lock"></a><a name="ctor"></a> improper_lock

Oluşturur `improper_lock exception` .

```cpp
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[critical_section sınıfı](critical-section-class.md)<br/>
[reader_writer_lock sınıfı](reader-writer-lock-class.md)

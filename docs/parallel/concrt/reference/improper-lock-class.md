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
ms.openlocfilehash: de7393c9186a1572040acd18854b5b3046b239f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552795"
---
# <a name="improperlock-class"></a>improper_lock Sınıfı

Bu sınıf, bir kilit alınmadığı yanlış olduğunda oluşturulan bir özel durum açıklar.

## <a name="syntax"></a>Sözdizimi

```
class improper_lock : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_lock](#ctor)|Fazla Yüklendi. Oluşturur bir `improper_lock exception`.|

## <a name="remarks"></a>Açıklamalar

Genellikle, bir reentrant olmayan kilit yinelemeli olarak aynı içerik üzerinde almaya denemesi yapıldığında bu özel durum oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_lock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> improper_lock

Oluşturur bir `improper_lock exception`.

```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[critical_section Sınıfı](critical-section-class.md)<br/>
[reader_writer_lock Sınıfı](reader-writer-lock-class.md)

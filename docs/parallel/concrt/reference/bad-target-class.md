---
title: bad_target Sınıfı
ms.date: 11/04/2016
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
ms.openlocfilehash: 0440955718bee3b426f5e4625b5eb3fc559a5d28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434489"
---
# <a name="badtarget-class"></a>bad_target Sınıfı

Bu sınıf, bir özel durum gerçekleştirilmekte olan işlem için geçersiz bir hedefe bir ileti bloğu bir işaretçi verildiğinde, durum açıklar.

## <a name="syntax"></a>Sözdizimi

```
class bad_target : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[bad_target](#ctor)|Fazla Yüklendi. Oluşturur bir `bad_target` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu özel durum, genellikle bir hedef için farklı bir hedef ayrılmış olan bir iletiyi kullanmak çalışan veya değil tutan bir ayırma serbest gibi nedenlerle oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`bad_target`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> bad_target

Oluşturur bir `bad_target` nesne.

```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../../parallel/concrt/asynchronous-message-blocks.md)


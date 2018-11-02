---
title: invalid_operation Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: 594c09ebedd2be55b288a7f31d55930244d80959
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473976"
---
# <a name="invalidoperation-class"></a>invalid_operation Sınıfı

Bu sınıf, daha doğru bir şekilde eşzamanlılık çalışma zamanı tarafından oluşturulan başka bir özel durum türü tarafından açıklanmayan geçersiz bir işlem gerçekleştirildiğinde verilen bir özel durumu anlatmaktadır.

## <a name="syntax"></a>Sözdizimi

```
class invalid_operation : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_operation](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_operation` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu özel durumun oluşturulacağı çeşitli yöntemler genellikle hangi durumlarda bunlar, altında oluşturulacağını belgeler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_operation`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> invalid_operation

Oluşturur bir `invalid_operation` nesne.

```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

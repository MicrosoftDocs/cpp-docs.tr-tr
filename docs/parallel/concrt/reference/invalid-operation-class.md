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
ms.openlocfilehash: e17d530569d16ba0084a58bf0be00d4a8423b7f6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140875"
---
# <a name="invalid_operation-class"></a>invalid_operation Sınıfı

Bu sınıf, Eşzamanlılık Çalışma Zamanı tarafından oluşturulan başka bir özel durum türü tarafından daha doğru bir şekilde açıklanmayan geçersiz bir işlem gerçekleştirildiğinde oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_operation : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_operation](#ctor)|Fazla Yüklendi. `invalid_operation` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu özel durumu oluşturan çeşitli yöntemler genellikle hangi koşullarda oluşturdukları konusunda belge oluşturur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_operation`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>invalid_operation

`invalid_operation` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

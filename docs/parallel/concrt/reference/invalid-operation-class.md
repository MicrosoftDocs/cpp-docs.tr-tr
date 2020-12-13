---
description: 'Hakkında daha fazla bilgi edinin: invalid_operation sınıfı'
title: invalid_operation Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: f3050d487f2c374f66f264b6e568fce5244d25ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334540"
---
# <a name="invalid_operation-class"></a>invalid_operation Sınıfı

Bu sınıf, Eşzamanlılık Çalışma Zamanı tarafından oluşturulan başka bir özel durum türü tarafından daha doğru bir şekilde açıklanmayan geçersiz bir işlem gerçekleştirildiğinde oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class invalid_operation : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_operation](#ctor)|Fazla Yüklendi. Bir `invalid_operation` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu özel durumu oluşturan çeşitli yöntemler genellikle hangi koşullarda oluşturdukları konusunda belge oluşturur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_operation`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_operation"></a><a name="ctor"></a> invalid_operation

Bir `invalid_operation` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)

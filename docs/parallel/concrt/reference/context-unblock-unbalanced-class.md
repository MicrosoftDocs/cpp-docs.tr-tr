---
title: context_unblock_unbalanced Sınıfı
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: 261ec96c1a83fbec423e6dbbfe403c4db53a2962
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143104"
---
# <a name="context_unblock_unbalanced-class"></a>context_unblock_unbalanced Sınıfı

Bu sınıf, bir `Context` nesnesinin `Block` ve `Unblock` yöntemlerine yapılan çağrılar düzgün şekilde eşleştirilmediğinde oluşan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Fazla Yüklendi. `context_unblock_unbalanced` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bir `Context` nesnesinin `Block` ve `Unblock` yöntemlerine yapılan çağrılar her zaman uygun şekilde eşleştirilmelidir. Eşzamanlılık Çalışma Zamanı işlemlerin her iki sırayla da gerçekleşmesini sağlar. Örneğin, bir `Block` çağrısının ardından `Unblock`veya tam tersi bir çağrı gelebilir. Bu özel durum, örneğin, bir satırda `Unblock` yöntemine yapılan iki çağrı, engellenmeyen bir `Context` nesnesi üzerinde yapılırsa oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>context_unblock_unbalanced

`context_unblock_unbalanced` nesnesi oluşturur.

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

---
description: 'Hakkında daha fazla bilgi edinin: context_unblock_unbalanced sınıfı'
title: context_unblock_unbalanced Sınıfı
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: d262ff52a675935f95664d2f7ddd69aa159aa0bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188969"
---
# <a name="context_unblock_unbalanced-class"></a>context_unblock_unbalanced Sınıfı

Bu sınıf, `Block` `Unblock` bir nesnenin ve yöntemlerine yapılan çağrılar `Context` düzgün şekilde eşleştirilmediğinde oluşan bir özel durum tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Fazla Yüklendi. Bir `context_unblock_unbalanced` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

`Block` `Unblock` Bir nesnenin ve yöntemlerine yapılan çağrılar `Context` her zaman uygun şekilde eşleştirilmelidir. Eşzamanlılık Çalışma Zamanı işlemlerin her iki sırayla da gerçekleşmesini sağlar. Örneğin, öğesine yapılan bir çağrı `Block` `Unblock` , veya tam tersi olabilir. Bu özel durum, örneğin, `Unblock` bir satırda yöntemine yapılan iki çağrı, engellenmeyen bir nesne üzerinde yapılırsa oluşturulur `Context` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="context_unblock_unbalanced"></a><a name="ctor"></a> context_unblock_unbalanced

Bir `context_unblock_unbalanced` nesnesi oluşturur.

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)

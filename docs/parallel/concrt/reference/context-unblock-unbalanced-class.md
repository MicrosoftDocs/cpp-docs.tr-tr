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
ms.openlocfilehash: f4f385cde2a27665afa5eb9869eb52bc42c70111
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296222"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne değil düzgün halindedir.

## <a name="syntax"></a>Sözdizimi

```
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Fazla Yüklendi. Oluşturur bir `context_unblock_unbalanced` nesne.|

## <a name="remarks"></a>Açıklamalar

Çağrılar `Block` ve `Unblock` yöntemlerinin bir `Context` nesne her zaman doğru eşleştirilmelidir. Eşzamanlılık Çalışma zamanı içinde herhangi bir sırada yapılması işlemlere izin verir. Örneğin, bir çağrı `Block` bir çağrı tarafından izlenebilir `Unblock`, veya tam tersi. Örneğin, iki çağrılar, bu özel durum `Unblock` üzerinde bir satır, metodu yapıldı bir `Context` değil engellendi nesnesidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> context_unblock_unbalanced

Oluşturur bir `context_unblock_unbalanced` nesne.

```
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)

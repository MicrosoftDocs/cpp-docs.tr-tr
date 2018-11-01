---
title: lock Sınıfı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 8876810b15a7d2736f2c8ab0ca1f4c6011918a5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547140"
---
# <a name="lock-class"></a>lock Sınıfı

Bu sınıf, erişim bir nesneye birden fazla iş parçacığından eşitlemek için bir kilit almayı otomatikleştirir.  Oluşturulan, kilit alır ve yayınlar kaldırıldığında kilidi.

## <a name="syntax"></a>Sözdizimi

```
ref class lock;
```

## <a name="remarks"></a>Açıklamalar

`lock` yalnızca CLR nesneler için kullanılabilir ve yalnızca CLR kod içinde kullanılabilir.

Dahili olarak, kilit sınıfı kullanır <xref:System.Threading.Monitor> erişimi eşitlemek için. Daha ayrıntılı bilgi için bu konudaki eşitleme konusuna bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[lock](../dotnet/lock.md)<br/>
[lock Üyeleri](../dotnet/lock-members.md)
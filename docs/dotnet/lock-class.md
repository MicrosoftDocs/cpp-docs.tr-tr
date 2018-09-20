---
title: lock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7ef0887ca3eec7510717aab21ba4c6c7aba98d25
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380301"
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
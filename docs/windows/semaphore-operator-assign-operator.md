---
title: Semaphore::operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b35268cd883245b125aa7c87919124b29451ff1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420328"
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator= İşleci

Belirtilen tanıtıcıdan taşır bir **semafor** geçerli nesneye **semafor** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Rvalue başvuru için bir **semafor** nesne.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru **semafor** nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Semafor Sınıfı](../windows/semaphore-class.md)
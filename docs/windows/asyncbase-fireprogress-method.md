---
title: AsyncBase::FireProgress yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d6cdab8d93394f4c51a4b99622d2f6f8604a87e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414701"
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress Yöntemi

Geçerli ilerleme olay işleyicisini çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Parametreler

*bağımsız değişken*<br/>
Çağrılacak olay işleyicisi yöntemi.

## <a name="remarks"></a>Açıklamalar

`ProgressTraits` türetilen [ArgTraitsHelper yapısı](../windows/argtraitshelper-structure.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)
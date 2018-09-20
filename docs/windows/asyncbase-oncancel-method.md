---
title: AsyncBase::OnCancel yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 346cb4049f0833bdbc950b6806177321d107db28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380743"
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel Yöntemi

Türetilen bir sınıfta geçersiz kılındığında, bir zaman uyumsuz işlem iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)<br/>
[AsyncBase::Cancel Metodu](../windows/asyncbase-cancel-method.md)
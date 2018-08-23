---
title: AsyncBase::FireCompletion yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs:
- C++
helpviewer_keywords:
- FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19b796b1fbc618bb909b186aa86d3c893c8536c5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600262"
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion Yöntemi

Tamamlanma olayı işleyicisini çağırır veya iç ilerleme temsilci sıfırlar.

## <a name="syntax"></a>Sözdizimi

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

## <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü **FireCompletion()** iç ilerleme temsilci değişkeni sıfırlar. Zaman uyumsuz işlem tamamlandıysa ikinci sürüm tamamlama olay işleyicisini çağırır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)
---
title: AsyncBase::CheckValidStateForDelegateCall yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForDelegateCall method
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3629fcaf8507abd2baf6cded3c6a63bc6fd64f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611506"
---
# <a name="asyncbasecheckvalidstatefordelegatecall-method"></a>AsyncBase::CheckValidStateForDelegateCall Yöntemi

Temsilci özellikleri geçerli zaman uyumsuz durumunda değiştirilebilir olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

## <a name="return-value"></a>Dönüş Değeri

Temsilci özellikleri değiştirilip değiştirilmediğini S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)
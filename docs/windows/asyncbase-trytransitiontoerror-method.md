---
title: AsyncBase::TryTransitionToError yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a6e21f89b5f1beb035b2dd87b2d0ad1d55bc3f8f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418066"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError Yöntemi

Belirtilen hata kodu iç hata durumunda değiştirip değiştiremeyeceğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Parametreler

*Hata*<br/>
HRESULT hatası.

## <a name="return-value"></a>Dönüş Değeri

**doğru** iç hata durumunda, değiştirilen; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Bu işlem, yalnızca hata durumunda S_OK için zaten ayarlanmışsa hata durumu değiştirir. Hata durumunda zaten iptal edildi, tamamlandı veya kapalı hata olması durumunda bu işlem bir etkisi yoktur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)
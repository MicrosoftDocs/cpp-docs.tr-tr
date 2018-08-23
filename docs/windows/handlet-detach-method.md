---
title: HandleT::Detach yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b66d5c65dd084da564067cd62242b315f6da182
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591380"
---
# <a name="handletdetach-method"></a>HandleT::Detach Yöntemi

Geçerli ayırır **HandleT** , temel alınan tanıtıcısını nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
typename HandleTraits::Type Detach();
```

## <a name="return-value"></a>Dönüş Değeri

Temel alınan tanıtıcısı.

## <a name="remarks"></a>Açıklamalar

Bu işlem tamamlandığında, geçerli **HandleT** geçersiz duruma ayarlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HandleT Sınıfı](../windows/handlet-class.md)
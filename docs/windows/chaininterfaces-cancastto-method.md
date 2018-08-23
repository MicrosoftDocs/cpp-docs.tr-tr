---
title: Chainınterfaces::cancastto yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8398f0bd4d9fdc786926782b13ebcac913a6a351
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612876"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo Yöntemi

Her varsayılan olmayan şablon parametreleri tarafından tanımlanan uzmanlıkları belirtilen arabirim kimliği içerip içermeyeceğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*riid*  
Bir arabirim kimliği.

*ppv*  
Atama başarıyla son arabirim kimliği için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**doğru** tüm atama işlemlerinin başarılı olduysa; Aksi takdirde, **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)
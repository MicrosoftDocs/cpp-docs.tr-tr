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
ms.openlocfilehash: 5839edd90f61f9f4aa96ea1d921d2179660be554
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461216"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo Yöntemi
Her varsayılan olmayan şablon parametreleri tarafından tanımlanan uzmanlıkları belirtilen arabirim kimliği içerip içermeyeceğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
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
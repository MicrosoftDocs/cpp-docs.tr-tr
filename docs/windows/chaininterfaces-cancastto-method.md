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
ms.openlocfilehash: c2286c347fbd68f34fac807e80facca0a0286aa6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo Yöntemi
Belirtilen arabirim kimliği her varsayılan olmayan şablon parametreleri tarafından tanımlanan özelleştirmeleri içerip içermeyeceğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Bir arabirim kimliği  
  
 `ppv`  
 Başarılı bir şekilde atama son arabirimi kimliği için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` tüm yayın operasyonlar başarılıysa; Aksi takdirde `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)
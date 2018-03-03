---
title: "AsyncBase::CheckValidStateForDelegateCall yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForDelegateCall method
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64c1a461712eb34fb8a113423c8ee18874aaf2d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasecheckvalidstatefordelegatecall-method"></a>AsyncBase::CheckValidStateForDelegateCall Yöntemi
Temsilci özellikleri geçerli zaman uyumsuz durumunda değiştirilebilir olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK temsilci özellikleri değiştirilebilir; Aksi takdirde E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)
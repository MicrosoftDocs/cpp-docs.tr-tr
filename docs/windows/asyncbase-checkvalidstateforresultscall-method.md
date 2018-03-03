---
title: "AsyncBase::CheckValidStateForResultsCall yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForResultsCall method
ms.assetid: 87ca6805-bff1-4063-b855-6dd26132deff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8918ad1ef10e8a349eb38b1a19604bdac1c5a92c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasecheckvalidstateforresultscall-method"></a>AsyncBase::CheckValidStateForResultsCall Yöntemi
Zaman uyumsuz bir işlem sonuçlarını geçerli zaman uyumsuz durumunda toplanabilir olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline HRESULT CheckValidStateForResultsCall();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK sonuçları toplanabilir; Aksi takdirde E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)
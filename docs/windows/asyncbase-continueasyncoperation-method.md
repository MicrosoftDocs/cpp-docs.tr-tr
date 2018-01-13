---
title: "AsyncBase::ContinueAsyncOperation yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs: C++
helpviewer_keywords: ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e86c4857aab7c0e1a23dcd03695d906a3d9e5e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation Yöntemi
Zaman uyumsuz işlem işleme devam etmesi gerektiğini veya durdurmak belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`zaman uyumsuz işlemi geçerli bir durumda olmadığını *başlatılan*, işlemi başka bir deyişle, devam etmelidir. Aksi takdirde, `false`, işlemi başka bir deyişle, durdurmak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)
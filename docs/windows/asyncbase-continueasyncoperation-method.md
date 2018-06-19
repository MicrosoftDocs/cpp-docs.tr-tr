---
title: AsyncBase::ContinueAsyncOperation yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: caf7cd1cbee97761c6877ec6ab3a51ea956cbfd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859598"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation Yöntemi
Zaman uyumsuz işlem işleme devam etmesi gerektiğini veya durdurmak belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` zaman uyumsuz işlemi geçerli bir durumda olmadığını *başlatılan*, işlemi başka bir deyişle, devam etmelidir. Aksi takdirde, `false`, işlemi başka bir deyişle, durdurmak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)
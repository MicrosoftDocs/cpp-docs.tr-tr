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
ms.openlocfilehash: e7b5d2b10b571a3517beab98eaa839d5c7fd86c2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460839"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation Yöntemi
Zaman uyumsuz işlem işlemeye devam etmesi gerektiğinin veya durdurmak belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** geçerli durumunu zaman uyumsuz işlemi ise *çalışmaya*, yani işlemi devam etmelidir. Aksi takdirde, **false**, yani işlemi durdurmak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)
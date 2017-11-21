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
ms.openlocfilehash: 976ee601e836bbabbfbf65beca41f6fbd687cebb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [AsyncBase sınıfı](../windows/asyncbase-class.md)
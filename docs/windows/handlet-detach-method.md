---
title: "HandleT::Detach yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b17d9f720d2fee92cfcf2aaf7b9f452cde32e3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="handletdetach-method"></a>HandleT::Detach Yöntemi
Temel alınan tutamacını geçerli HandleT nesnesinden keser.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Temel alınan işleci.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem tamamlandığında, geçerli HandleT geçersiz durumuna ayarlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT sınıfı](../windows/handlet-class.md)
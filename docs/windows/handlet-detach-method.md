---
title: HandleT::Detach yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 100d215099494c9b2714fd2c42dee69644a5006c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
 [HandleT Sınıfı](../windows/handlet-class.md)
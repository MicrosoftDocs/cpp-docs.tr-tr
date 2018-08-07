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
ms.openlocfilehash: cc11d6be992584adb1ce2075e73d080cc3a43f47
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569485"
---
# <a name="handletdetach-method"></a>HandleT::Detach Yöntemi
Geçerli ayırır **HandleT** , temel alınan tanıtıcısını nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Temel alınan tanıtıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem tamamlandığında, geçerli **HandleT** geçersiz duruma ayarlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)
---
title: AsyncBase::CurrentStatus yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 316dfea16aa129dcaff42424bef46305d2dd56b4
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461435"
---
# <a name="asyncbasecurrentstatus-method"></a>AsyncBase::CurrentStatus Yöntemi
Geçerli zaman uyumsuz işlemin durumunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Durumu*  
 Bu işlem geçerli durumu depoladığı konum.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem, iş parçacığı açısından güvenlidir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)   
 [AsyncStatusInternal Sabit Listesi](../windows/asyncstatusinternal-enumeration.md)
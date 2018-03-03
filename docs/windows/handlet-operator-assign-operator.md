---
title: "HandleT::operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68afd6b2a0a1c17cd032d6cea84aefde8c368204
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handletoperator-operator"></a>HandleT::operator= İşleci
Belirtilen HandleT nesnenin değerini geçerli HandleT nesneye taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Bir rvalue başvuru bir işlenecek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli HandleT nesneye başvuru.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem parametresi tarafından belirtilen HandleT nesnesi geçersiz kılar `h`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)
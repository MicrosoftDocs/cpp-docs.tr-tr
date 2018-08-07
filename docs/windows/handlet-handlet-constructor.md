---
title: HandleT::HandleT Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f8126d4a31863ab556295946ffc170fc49f7d98
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569517"
---
# <a name="handlethandlet-constructor"></a>HandleT::HandleT Oluşturucusu
Yeni bir örneğini başlatır **HandleT** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *h*  
 Tanıtıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu başlatan bir **HandleT** değil bir nesne için geçerli bir tanıtıcı nesnesi. İkinci oluşturucu yeni bir oluşturur **HandleT** parametre nesneden *h*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)
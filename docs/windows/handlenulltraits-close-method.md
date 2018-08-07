---
title: HANDLENullTraits::Close yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3bc6e7adfa99e2ce25c9913309b5c5bd486bee0
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569407"
---
# <a name="handlenulltraitsclose-method"></a>HANDLENullTraits::Close Yöntemi
Belirtilen tanıtıcı kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *h*  
 Kapatmak için tanıtıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** , tanıtıcı *h* kapalı başarıyla; Aksi takdirde **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HANDLENullTraits Yapısı](../windows/handlenulltraits-structure.md)
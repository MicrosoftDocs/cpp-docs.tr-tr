---
title: "HANDLENullTraits::Close yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbe3f8ebe8c63eda026da92aec037037830a763d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handlenulltraitsclose-method"></a>HANDLENullTraits::Close Yöntemi
Belirtilen tanıtıcı kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Kapatmak için işleci.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa işlemek `h` kapalı başarıyla; Aksi halde, **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HANDLENullTraits Yapısı](../windows/handlenulltraits-structure.md)
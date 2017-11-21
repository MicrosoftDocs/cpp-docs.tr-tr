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
ms.openlocfilehash: 45d92fd9d14fa65594db17ce881eb0821810b1dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [HANDLENullTraits yapısı](../windows/handlenulltraits-structure.md)
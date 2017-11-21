---
title: "HANDLETraits::Close yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1acb5125f8d38704b805885ad318c2bd301bcb7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="handletraitsclose-method"></a>HANDLETraits::Close Yöntemi
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
 [HANDLETraits yapısı](../windows/handletraits-structure.md)
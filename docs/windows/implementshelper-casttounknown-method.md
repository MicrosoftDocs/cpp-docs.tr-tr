---
title: "Implementshelper::casttounknown yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs: C++
helpviewer_keywords: CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66e45448d25cff013ad4a0d98e8cca403589581b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementshelpercasttounknown-method"></a>ImplementsHelper::CastToUnknown Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Temel alınan IUnknown arabirimi işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işaretçi temel IUnknown arabirimi için geçerli Implements yapısı alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implementshelper yapısı](../windows/implementshelper-structure.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)
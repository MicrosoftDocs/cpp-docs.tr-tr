---
title: "Creatormap::activationıd veri üyesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::CreatorMap::activationId
dev_langs: C++
helpviewer_keywords: activationId data member
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d1bd0e310f5c0bc4afcb967dc141776aeb236fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creatormapactivationid-data-member"></a>CreatorMap::activationId Veri Üyesi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## <a name="parameters"></a>Parametreler  
 `clsid`  
 Bir arabirim kimliği  
  
 `getRuntimeName`  
 Bir nesnenin Windows çalışma zamanı adını alır. bir işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir klasik COM sınıfı kimliği veya bir Windows çalışma zamanı adı tarafından tanımlanan bir nesne kimliği temsil eder.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CreatorMap yapısı](../windows/creatormap-structure.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)
---
title: "Cloakedıid yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::CloakedIid
dev_langs: C++
helpviewer_keywords: CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a10752fecadaf3a7f044e3c563931ae3cdbe1b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cloakediid-structure"></a>CloakedIid Yapısı
RuntimeClass, uygular ve Chainınterfaces şablonların belirtilen arabirim IID listesinde erişilebilir değil gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 (Örtülmüş) gizlenen arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 Cloakedıid nasıl kullanıldığı bir örnek şudur: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)
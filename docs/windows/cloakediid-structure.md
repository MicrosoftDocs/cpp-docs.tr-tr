---
title: "Cloakedıid yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c61e005759af9b5fde4bfff407ed502a41c22a72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
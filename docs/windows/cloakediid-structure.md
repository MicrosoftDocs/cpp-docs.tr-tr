---
title: Cloakedıid yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 57ad76b48b92519eaeed089dfb14817c38273588
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856166"
---
# <a name="cloakediid-structure"></a>CloakedIid Yapısı
RuntimeClass, uygular ve Chainınterfaces şablonların belirtilen arabirim IID listesinde erişilebilir değil gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
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
---
title: "RuntimeClassFlags yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassFlags
dev_langs: C++
helpviewer_keywords: RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85eb42c537845d86ce8cf3b1f20db7e9eeffe76f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags Yapısı
Öğesinin bir örneği için türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `flags`  
 A [RuntimeClassType numaralandırması](../windows/runtimeclasstype-enumeration.md) değeri.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RuntimeClassFlags::value Sabiti](../windows/runtimeclassflags-value-constant.md)|İçeren bir [RuntimeClassType numaralandırması](../windows/runtimeclasstype-enumeration.md) değeri.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
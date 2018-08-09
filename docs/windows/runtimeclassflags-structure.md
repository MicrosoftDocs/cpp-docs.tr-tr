---
title: RuntimeClassFlags yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 823244b54513e4f6b2901bc29984604f65eb9a11
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018042"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags Yapısı
Örneğinin türünü içeren bir [RuntimeClass](../windows/runtimeclass-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
### <a name="parameters"></a>Parametreler  
 *bayrakları*  
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
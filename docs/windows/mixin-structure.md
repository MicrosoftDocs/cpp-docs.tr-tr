---
title: Mixın yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
dev_langs:
- C++
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0ebf8efb556aef4fbd5048fa1930f2d98a01410
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605730"
---
# <a name="mixin-structure"></a>MixIn Yapısı
Bir çalışma zamanı sınıf varsa Windows çalışma zamanı arabirimleri ve ardından klasik COM arabirimleri türetilen sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
### <a name="parameters"></a>Parametreler  
 *Türetilmiş*  
 Türetilmiş bir tür [uygular](../windows/implements-structure.md) yapısı.  
  
 *MixInType*  
 Bir taban türü.  
  
 *hasImplements*  
 **doğru** varsa *MixInType* olan geçerli uygulamasından türetilmiş temel tür; **false** Aksi takdirde.  
  
## <a name="remarks"></a>Açıklamalar  
 Windows çalışma zamanı hem sınıf COM arabirimleri türetilmiş bir sınıf, sınıf bildirimi listesi Windows çalışma zamanı arabirimlerden önce listelemesi gerekir ve ardından tüm klasik COM arabirimleri. **MixIn** arabirimler doğru sırada belirtilir sağlar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `MixIn`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
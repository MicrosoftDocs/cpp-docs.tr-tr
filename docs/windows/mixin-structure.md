---
title: "Mixın yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::MixIn
dev_langs: C++
helpviewer_keywords: MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 883e952dde579cce3f5a65ba4a453f98ddbb4740
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mixin-structure"></a>MixIn Yapısı
Bir çalışma zamanı sınıf Windows Çalışma Zamanı Modülü arabirimler, varsa ve daha sonra klasik COM arabirimleri türetilen sağlar.  
  
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
  
#### <a name="parameters"></a>Parametreler  
 `Derived`  
 Öğesinden türeyen bir tür [uygulayan](../windows/implements-structure.md) yapısı.  
  
 `MixInType`  
 Bir taban türü.  
  
 `hasImplements`  
 `true`varsa `MixInType` olan geçerli uygulamasından türetilmiş temel türü; `false` Aksi takdirde.  
  
## <a name="remarks"></a>Açıklamalar  
 Windows çalışma zamanı hem sınıfı COM arabirimleri türetilmiş bir sınıf, sınıf bildirimi önce tüm Windows Çalışma Zamanı Modülü arabirimler listesi gerekir ve tüm klasik COM arabirimleri. MixIn arabirimler doğru sırayla belirtilir sağlar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `MixIn`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
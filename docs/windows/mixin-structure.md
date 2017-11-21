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
ms.openlocfilehash: e1df2de0a8c645b957a5c3e93f8c4ebbb3b2fb94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)
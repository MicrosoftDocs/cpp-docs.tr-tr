---
title: WeakReference Class1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference
dev_langs: C++
helpviewer_keywords: WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb8e05ca3ef52515af58db455ed83da593d6bdfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="weakreference-class1"></a>WeakReference Class1
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class WeakReference;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Temsil eden bir *zayıf başvuru* kullanılabilecek Windows çalışma zamanı veya klasik COM Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.  
  
 A `WeakReference` nesne tutan bir *güçlü başvuru*, bir nesne için bir işaretçi olduğu ve *güçlü başvuru sayısı*, tarafından dağıtılan güçlü başvuru kopya sayısını olduğu Resolve() yöntemi. Güçlü Başvuru sayısı sıfır olsa da, güçlü başvurunun geçerli olduğundan ve erişilebilir bir nesnedir. Güçlü Başvuru sayısı sıfır olduğunda, güçlü başvuru geçersiz ve nesne erişilemez.  
  
 WeakReference nesne, genellikle, varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil etmek için kullanılır. Örneğin, bir dosya nesnesine başvuru WeakReference nesnesinden oluşturun. Dosya açıkken güçlü başvurusu geçerli değil. Ancak dosyayı kapattıysanız, güçlü başvuru geçersiz hale gelir.  
  
 İş parçacığı içinde korumalı WeakReference yöntemleridir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[WeakReference::WeakReference Oluşturucusu](../windows/weakreference-weakreference-constructor.md)|WeakReference sınıfı yeni bir örneğini başlatır.|  
|[WeakReference:: ~ WeakReference yok Edicisi](../windows/weakreference-tilde-weakreference-destructor.md)|Deinitializes (bozar) WeakReference sınıfının geçerli örneği.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[WeakReference::DecrementStrongReference yöntemi](../windows/weakreference-decrementstrongreference-method.md)|Güçlü Başvuru azaltır geçerli WeakReference nesne sayısı.|  
|[Weakreference::ıncrementstrongreference yöntemi](../windows/weakreference-incrementstrongreference-method.md)|Geçerli WeakReference nesnesinin güçlü başvuru sayısını artırır.|  
|[WeakReference::Resolve yöntemi](../windows/weakreference-resolve-method.md)|Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.|  
|[WeakReference::SetUnknown yöntemi](../windows/weakreference-setunknown-method.md)|Güçlü Başvuru geçerli WeakReference nesnenin belirtilen arabirimi işaretçisi ayarlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `WeakReference`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)
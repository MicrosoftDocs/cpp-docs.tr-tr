---
title: WeakReference::Resolve yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe78f8644768563507f98157ac859993776d7fe9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646208"
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *riid*  
 Bir arabirim kimliği.  
  
 *ppvObject*  
 Bu işlem tamamlandığında bir kopyasını güçlü başvuru sayısı sıfır değilse geçerli güçlü başvuru.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
-   Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır olan. *PpvObject* parametrenin ayarlanmış **nullptr**.  
  
-   Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır. *PpvObject* parametre güçlü başvuru.  
  
-   Aksi takdirde, nedenini belirten bir HRESULT, bu işlem başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakReference sınıfı1](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
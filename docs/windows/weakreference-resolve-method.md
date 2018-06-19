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
ms.openlocfilehash: dccdf7554f8d102230bedc18231feb74625d621b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890482"
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
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Bir arabirim kimliği  
  
 `ppvObject`  
 Bu işlem tamamlandığında, bir kopyasını güçlü başvuru sayısı sıfır değilse geçerli güçlü başvuru.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
-   Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır değil. `ppvObject` Parametrenin ayarlanmış `nullptr`.  
  
-   Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır olmayan bir değer. `ppvObject` Güçlü başvuru parametresini ayarlayın.  
  
-   Aksi takdirde, nedenini belirten bir HRESULT bu işlemi başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WeakReference Class1](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
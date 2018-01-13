---
title: "ActivationFactoryCallback işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs: C++
helpviewer_keywords: ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e88a6f9cb89746cd0380587789fbdd68f80d5e36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `activationId`  
 Bir çalışma zamanı sınıf adını belirten bir dizeyi işler.  
  
 `ppFactory`  
 Bu işlem tamamlandığında, parametresine karşılık gelen bir etkinleştirme Fabrika `activationId`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata açıklar. Büyük olasılıkla hata HRESULTs CLASS_E_CLASSNOTAVAILABLE ve E_INVALIDARG verilmiştir.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen etkinleştirme kimliği için etkinleştirme üretecini alır  
  
 Windows Çalışma Zamanı Modülü çalışma zamanı sınıf adını kullanarak belirtilen bir nesne istemek için bu geri çağırma işlevini çağırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
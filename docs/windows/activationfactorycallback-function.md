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
ms.openlocfilehash: adf41c8a518b0ca57326da1dd71c1a8ddd6f0a27
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)
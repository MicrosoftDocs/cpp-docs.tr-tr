---
title: ActivationFactoryCallback işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f1bae2c503f4e5f0c887a46956248184ece9a1e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857330"
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
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
ms.openlocfilehash: 858232702367aef62d0228f2e8653774896bd87f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647189"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Activationıd*  
 Bir çalışma zamanı sınıfı adının belirten bir dize için işler.  
  
 *ppFactory*  
 Bu işlem tamamlandığında, parametresine karşılık geldiği bir etkinleştirme fabrikası *Activationıd*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. Büyük olasılıkla başarısız HRESULTs, CLASS_E_CLASSNOTAVAILABLE ve E_INVALIDARG verilmiştir.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen etkinleştirme kimliği için kullanılan etkinleştirme üreteci alır  
  
 Windows çalışma zamanı ve çalışma zamanı sınıf adıyla belirtilen bir nesne istemek için bu geri çağırma işlevini çağırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
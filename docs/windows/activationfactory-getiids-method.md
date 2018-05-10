---
title: Activationfactory::getıids yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f411f3b2f9e777a4e458b64176ace77a8d13e86
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="activationfactorygetiids-method"></a>ActivationFactory::GetIids Metodu
Uygulanan arabirimi kimlikleri dizisini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `iidCount`  
 Bu işlem tamamlandığında, interace kimlikleri sayısı `iids` dizi.  
  
 `iids`  
 Bu işlem tamamlandığında, bir dizi arabirim kimlikleri uygulanmadı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata açıklar. E_OUTOFMEMORY, HRESULT olası bir hatadır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActivationFactory Sınıfı](../windows/activationfactory-class.md)
---
title: "Activationfactory::getıids yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs: C++
helpviewer_keywords: GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4fb9d71da187e12f119dd9b020e1bbab730855c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [ActivationFactory sınıfı](../windows/activationfactory-class.md)
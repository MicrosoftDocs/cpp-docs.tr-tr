---
title: GetActivationFactory işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd269b8c2e1c671944305d385064d60e8bf9b8a1
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="getactivationfactory-function"></a>GetActivationFactory İşlevi
Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üreteci alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon parametresi etkinleştirme Fabrika türünü belirtir.  
  
 `activatableClassId`  
 Etkinleştirme üretecin üretebileceği sınıfı adı.  
  
 `factory`  
 Bu işlem tamamlandığında, etkinleştirme Fabrika türü için bir başvuru `T`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, bu işlemi neden başarısız gösterir HRESULT hata.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Windows::Foundation  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation Ad Alanı](../windows/windows-foundation-namespace.md)
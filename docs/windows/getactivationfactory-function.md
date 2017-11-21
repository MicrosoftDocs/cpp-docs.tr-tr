---
title: "GetActivationFactory işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs: C++
helpviewer_keywords: GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 34ffd1826e337194e83e4fa7741e18f7892a47cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getactivationfactory-function"></a>GetActivationFactory İşlevi
Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üreteci alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename T  
>  
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
 [Windows::Foundation Namespace](../windows/windows-foundation-namespace.md)
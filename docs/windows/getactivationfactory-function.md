---
title: GetActivationFactory işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2cbb5be3603f79a7df1cb330ca06775357666854
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570317"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory İşlevi
Şablon parametresi tarafından belirtilen tür için bir etkinleştirme üretecini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Şablon parametresi etkinleştirme fabrikası türünü belirtir.  
  
 *activatableClassId*  
 Etkinleştirme üretecin üretebileceği sınıfı adı.  
  
 *Fabrika*  
 Bu işlem tamamlandığında, bir başvuru türü için etkinleştirme fabrikası *T*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, bu işlem başarısız olmasının gösteren HRESULT hatası.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Windows::Foundation  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows::Foundation Ad Alanı](../windows/windows-foundation-namespace.md)
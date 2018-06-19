---
title: ComPtr::ComPtr Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3a632c96c39ccd40f008556287af95944530cdc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871181"
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr Oluşturucusu
ComPtr sınıfı yeni bir örneğini intializes. Aşırı varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `U`  
 `other` parametresinin türü.  
  
 `other`  
 Türünde bir nesne `U`.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu hangi implictly boş bir nesne oluşturur varsayılan oluşturucu, ' dir. İkinci oluşturucu belirtir [__nullptr](../windows/nullptr-cpp-component-extensions.md), boş bir nesne açıkça oluşturulur.  
  
 Üçüncü Oluşturucusu bir işaretçi tarafından belirtilen nesne bir nesne oluşturur.  
  
 Dördüncü ve beşinci oluşturucular kopya oluşturucuları ' dir. Geçerli türüne dönüştürülebilir ise beşinci Oluşturucusu nesne kopyalar.  
  
 Altıncı ve yedinci oluşturucular taşıma oluşturucuları ' dir. Geçerli türüne dönüştürülebilir ise yedinci Oluşturucusu nesneyi taşır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)
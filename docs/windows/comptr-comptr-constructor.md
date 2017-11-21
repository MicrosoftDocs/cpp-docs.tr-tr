---
title: "ComPtr::ComPtr Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ComPtr
dev_langs: C++
helpviewer_keywords: ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b31fdcbad35bc65b2d8ca26ccab69e875c1d3aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr Oluşturucusu
ComPtr sınıfı yeni bir örneğini intializes. Aşırı varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
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
 [ComPtr sınıfı](../windows/comptr-class.md)
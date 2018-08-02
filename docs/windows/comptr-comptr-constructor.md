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
ms.openlocfilehash: d08eb264ff3b4fc2f0170d6aee742ff29611613e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465376"
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr Oluşturucusu
Yeni bir örneğini başlatır **ComPtr** sınıfı. Varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları aşırı yüklemeler sağlar.  
  
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
 *U*  
 Türünü *diğer* parametresi.  
  
 *Diğer*  
 Bir nesne türü *U*.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu boş bir nesneye hangi insert oluşturur varsayılan oluşturucudur. İkinci oluşturucu belirtir [__nullptr](../windows/nullptr-cpp-component-extensions.md), boş bir nesneye açıkça oluşturulur.  
  
 Üçüncü Oluşturucu bir işaretçi tarafından belirtilen nesne bir nesne oluşturur.  
  
 Dördüncü ve beşinci oluşturucular kopya oluşturucuları ' dir. Geçerli türüne dönüştürülebilir ise beşinci Oluşturucu nesneyi kopyalar.  
  
 Altıncı ve yedinci oluşturucular taşıma oluşturucuları ' dir. Geçerli türüne dönüştürülebilir ise yedinci Oluşturucusu bir nesneyi taşır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)
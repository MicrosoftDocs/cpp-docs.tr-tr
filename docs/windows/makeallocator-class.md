---
title: MakeAllocator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33ba172099fd2554709cc539eeee8999c0e42cef
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="makeallocator-class"></a>MakeAllocator Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;  
  
template<typename T>  
class MakeAllocator<T, false>;  
  
template<typename T>  
class MakeAllocator<T, true>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Tür adı.  
  
 `hasWeakReferenceSupport`  
 `true` zayıf başvurular destekleyen bir nesne için bellek ayrılamadı; `false` zayıf başvurular desteklemeyen bir nesne için bellek ayrılamadı.  
  
## <a name="remarks"></a>Açıklamalar  
 Zayıf başvuru desteği olmadan veya ile bir activatable sınıfı için bellek ayırır.  
  
 MakeAllocator sınıfı, bir kullanıcı tarafından tanımlanan bellek ayırma modeli uygulamak için geçersiz kılar.  
  
 MakeAllocator genellikle bir nesne oluşturma sırasında oluşturursa bellek sızıntıları önlemek için kullanılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MakeAllocator::MakeAllocator Oluşturucusu](../windows/makeallocator-makeallocator-constructor.md)|MakeAllocator sınıfı yeni bir örneğini başlatır.|  
|[MakeAllocator::~MakeAllocator Yıkıcısı](../windows/makeallocator-tilde-makeallocator-destructor.md)|MakeAllocator sınıfı, geçerli örneğini deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MakeAllocator::Allocate Metodu](../windows/makeallocator-allocate-method.md)|Bellek ayırır ve geçerli MakeAllocator nesnesi ile ilişkilendirir.|  
|[MakeAllocator::Detach Metodu](../windows/makeallocator-detach-method.md)|Tarafından ayrılan bellek keser [ayırma](../windows/makeallocator-allocate-method.md) geçerli MakeAllocator nesnesinden yöntemi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `MakeAllocator`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
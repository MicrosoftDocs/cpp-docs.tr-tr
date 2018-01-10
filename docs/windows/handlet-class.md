---
title: "HandleT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs: C++
helpviewer_keywords: HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ff7261735149abb8db607c5fc0cd4aa837fdfd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handlet-class"></a>HandleT Sınıfı
Bir tanıtıcı nesneyi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `HandleTraits`  
 Örneği [HandleTraits](../windows/handletraits-structure.md) bir tanıtıcı ortak özelliklerini tanımlayan yapıda.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Traits`|Eşanlamlısı `HandleTraits`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HandleT::HandleT Oluşturucusu](../windows/handlet-handlet-constructor.md)|HandleT sınıfı yeni bir örneğini başlatır.|  
|[HandleT::~HandleT Yıkıcısı](../windows/handlet-tilde-handlet-destructor.md)|HandleT sınıfı örneği deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HandleT::Attach Metodu](../windows/handlet-attach-method.md)|Belirtilen tanıtıcı geçerli HandleT nesnesi ile ilişkilendirir.|  
|[HandleT::Close Metodu](../windows/handlet-close-method.md)|Geçerli HandleT nesnesini kapatır.|  
|[HandleT::Detach Metodu](../windows/handlet-detach-method.md)|Temel alınan tutamacını geçerli HandleT nesnesinden keser.|  
|[HandleT::Get Metodu](../windows/handlet-get-method.md)|Temel alınan tanıtıcı değerini alır.|  
|[HandleT::IsValid Metodu](../windows/handlet-isvalid-method.md)|Geçerli HandleT nesne bir tanıtıcı temsil edip etmediğini gösterir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HandleT::InternalClose Metodu](../windows/handlet-internalclose-method.md)|Geçerli HandleT nesnesini kapatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HandleT::operator= İşleci](../windows/handlet-operator-assign-operator.md)|Belirtilen HandleT nesnenin değerini geçerli HandleT nesneye taşır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HandleT::handle_ Veri Üyesi](../windows/handlet-handle-data-member.md)|HandleT nesnesi tarafından temsil edilen tanıtıcıyı içerir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HandleT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)
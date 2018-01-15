---
title: "Interfacetraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs: C++
helpviewer_keywords: InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c28c7c1eef2fc278a0667ec4b7c635005331467
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraits-structure"></a>InterfaceTraits Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `I0`  
 Arabirim adı.  
  
 `CloakedType`  
 RuntimeClass, uygular ve Chainınterfaces, arabirim kimlikleri listesinde olmayacak bir arabirim desteklenmiyor.  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirim genel özelliklerini uygular.  
  
 İkinci bir uzmanlık gizlenmiş arabirimleri için şablonudur. Nil parametreleri için özelleştirmesi üçüncü şablonudur.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Base`|Eşanlamlısı `I0` şablon parametresi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo Metodu](../windows/interfacetraits-cancastto-method.md)|Bir işaretçi için belirtilen işaretçi içerip içermeyeceğini gösterir `Base`.|  
|[InterfaceTraits::CastToBase Metodu](../windows/interfacetraits-casttobase-method.md)|Bir işaretçi belirtilen işaretçisine bıraktığı `Base`.|  
|[InterfaceTraits::CastToUnknown Metodu](../windows/interfacetraits-casttounknown-method.md)|IUnknown işaretçisi belirtilen işaretçisine çevirir.|  
|[InterfaceTraits::FillArrayWithIid Metodu](../windows/interfacetraits-fillarraywithiid-method.md)|Arabirim kimliği atar `Base` dizini bağımsız değişkeniyle belirtilen dizi öğesi.|  
|[InterfaceTraits::Verify Metodu](../windows/interfacetraits-verify-method.md)|Temel düzgün türetilmiş doğrular.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[InterfaceTraits::IidCount Sabiti](../windows/interfacetraits-iidcount-constant.md)|Kimlikleri geçerli Interfacetraits nesneyle ilişkili arabirimi sayısını tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `InterfaceTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
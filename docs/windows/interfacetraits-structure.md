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
ms.openlocfilehash: 494942ce3c50889cae7a8867dc2b86ed6a609313
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[Interfacetraits::cancastto yöntemi](../windows/interfacetraits-cancastto-method.md)|Bir işaretçi için belirtilen işaretçi içerip içermeyeceğini gösterir `Base`.|  
|[Interfacetraits::casttobase yöntemi](../windows/interfacetraits-casttobase-method.md)|Bir işaretçi belirtilen işaretçisine bıraktığı `Base`.|  
|[Interfacetraits::casttounknown yöntemi](../windows/interfacetraits-casttounknown-method.md)|IUnknown işaretçisi belirtilen işaretçisine çevirir.|  
|[Interfacetraits::fillarraywithıid yöntemi](../windows/interfacetraits-fillarraywithiid-method.md)|Arabirim kimliği atar `Base` dizini bağımsız değişkeniyle belirtilen dizi öğesi.|  
|[Interfacetraits::Verify yöntemi](../windows/interfacetraits-verify-method.md)|Temel düzgün türetilmiş doğrular.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Interfacetraits::ıidcount sabiti](../windows/interfacetraits-iidcount-constant.md)|Kimlikleri geçerli Interfacetraits nesneyle ilişkili arabirimi sayısını tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `InterfaceTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)
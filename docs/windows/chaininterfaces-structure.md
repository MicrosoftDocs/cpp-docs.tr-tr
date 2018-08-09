---
title: Chainınterfaces yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7765ab5159f7cfd604f67b79a05fde8eaf57fad8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646711"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces Yapısı
Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
### <a name="parameters"></a>Parametreler  
 *I0*  
 (Gerekli) Arabirim Kimliği: 0.  
  
 *I1*  
 (Gerekli) Arabirim kimliği 1.  
  
 *I2*  
 (İsteğe bağlı) Arabirim kimliği 2.  
  
 *I3*  
 (İsteğe bağlı) Arabirim Kimliği 3.  
  
 *I4*  
 (İsteğe bağlı) Arabirim Kimliği 4.  
  
 *I5*  
 (İsteğe bağlı) Arabirim kimliği 5.  
  
 *I6*  
 (İsteğe bağlı) Arabirim kimliği 6.  
  
 *I7*  
 (İsteğe bağlı) Arabirim kimliği 7.  
  
 *I8*  
 (İsteğe bağlı) 8 arabirim kimliği.  
  
 *I9*  
 (İsteğe bağlı) Arabirim Kimliği 9.  
  
 *DerivedType*  
 Türetilmiş bir tür.  
  
 *BaseType*  
 Türetilmiş türün temel türü.  
  
 *hasImplements*  
 Bir Boole değeri olması durumunda **true**, kullanamazsınız anlamına gelir. bir [MixIn](../windows/mixin-structure.md) türünden türemez bir sınıf ile yapı [uygular](../windows/implements-structure.md) yapıda.  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo Metodu](../windows/chaininterfaces-cancastto-method.md)|Her tarafından tanımlanan uzmanlıkları belirtilen arabirim kimliği içerip içermeyeceğini belirten **ChainInterface** şablon parametreleri.|  
|[ChainInterfaces::CastToUnknown Metodu](../windows/chaininterfaces-casttounknown-method.md)|Arabirim işaretçisi tarafından tanımlanan tür yayınlar *I0* şablon parametresi için bir işaretçi olarak `IUnknown`.|  
|[ChainInterfaces::FillArrayWithIid Metodu](../windows/chaininterfaces-fillarraywithiid-method.md)|Arabirim kimliği tarafından tanımlanan depoları *I0* şablon parametresi belirtilen bir dizisinde belirtilen bir konuma arabiriminin kimlikleri.|  
|[ChainInterfaces::Verify Metodu](../windows/chaininterfaces-verify-method.md)|Her arabirim şablon parametreleri tarafından tanımlanan doğrular *I0* aracılığıyla *I9* devraldığı `IUnknown` ve/veya `IInspectable`ve *I0* devralır *I1* aracılığıyla *I9*.|  
  
### <a name="protected-constants"></a>Korumalı sabitleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ChainInterfaces::IidCount Sabiti](../windows/chaininterfaces-iidcount-constant.md)|Arabirim kimlikleri şablon parametreleri tarafından belirtilen arabirimlerden bulunan toplam sayısı *I0* aracılığıyla *I9*.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
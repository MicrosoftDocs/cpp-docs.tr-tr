---
title: "Chainınterfaces yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e9417b3950e4df98ed4e13ea1bb40e76c383868e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces Yapısı
Arabirim kimlikleri kümesine uygulanabilir doğrulama ve başlatma işlevleri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `I0`  
 (Gerekli) Kimliği 0 arabirim.  
  
 `I1`  
 (Gerekli) Arabirim kimliği 1.  
  
 `I2`  
 (İsteğe bağlı) Arabirim kimliği 2.  
  
 `I3`  
 (İsteğe bağlı) Arabirim Kimliği 3.  
  
 `I4`  
 (İsteğe bağlı) Arabirim Kimliği 4.  
  
 `I5`  
 (İsteğe bağlı) Arabirim kimliği 5.  
  
 `I6`  
 (İsteğe bağlı) Arabirim kimliği 6.  
  
 `I7`  
 (İsteğe bağlı) Arabirim kimliği 7.  
  
 `I8`  
 (İsteğe bağlı) Arabirim kimliği 8.  
  
 `I9`  
 (İsteğe bağlı) Arabirim Kimliği 9.  
  
 `DerivedType`  
 Türetilmiş bir tür.  
  
 `BaseType`  
 Türetilmiş bir tür temel türü.  
  
 `hasImplements`  
 Bir Boole değeri olması durumunda `true`, kullanamazsınız anlamına gelir bir [MixIn](../windows/mixin-structure.md) türünden türemez bir sınıf yapısıyla [uygulayan](../windows/implements-structure.md) yapıda.  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo Metodu](../windows/chaininterfaces-cancastto-method.md)|Belirtilen arabirim kimliği her ChainInterface şablon parametreleri tarafından tanımlanan özelleştirmeleri içerip içermeyeceğini gösterir.|  
|[ChainInterfaces::CastToUnknown Metodu](../windows/chaininterfaces-casttounknown-method.md)|Arabirim işaretçisi tarafından tanımlanan türdeki bıraktığı `I0` şablon parametresi IUnknown işaretçisi olarak.|  
|[ChainInterfaces::FillArrayWithIid Metodu](../windows/chaininterfaces-fillarraywithiid-method.md)|Arabirim kimliği tarafından tanımlanan depoları `I0` belirtilen dizinin içinde belirtilen bir konuma kimlikleri arabiriminin şablon parametresi.|  
|[ChainInterfaces::Verify Metodu](../windows/chaininterfaces-verify-method.md)|Her bir arabirime şablon parametreleri tarafından tanımlanan doğrular `I0` aracılığıyla `I9` IUnknown ve/veya Iınspectable ve, devralan `I0` devraldığı `I1` aracılığıyla `I9`.|  
  
### <a name="protected-constants"></a>Korumalı sabitleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ChainInterfaces::IidCount Sabiti](../windows/chaininterfaces-iidcount-constant.md)|Arabirim şablon parametresi tarafından belirtilen arabirimler içinde yer alan kimlikleri toplam sayısı `I0` aracılığıyla `I9`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
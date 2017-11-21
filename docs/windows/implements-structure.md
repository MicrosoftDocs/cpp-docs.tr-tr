---
title: "Uygulayan yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements
dev_langs: C++
helpviewer_keywords: Implements structure
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dc11fac57cc70e1556e681ab43fd48ce695a4a6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implements-structure"></a>Implements Yapısı
QueryInterface ve GetIid için belirtilen arabirimlerini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `I0`  
 Sıfırıncı arabirimi kimliği (Zorunlu)  
  
 `I1`  
 İlk arabirimi kimliği. (İsteğe bağlı)  
  
 `I2`  
 İkinci arabirimi kimliği. (İsteğe bağlı)  
  
 `I3`  
 Üçüncü arabirimi kimliği. (İsteğe bağlı)  
  
 `I4`  
 Dördüncü arabirimi kimliği. (İsteğe bağlı)  
  
 `I5`  
 Beşinci arabirimi kimliği. (İsteğe bağlı)  
  
 `I6`  
 Altıncı arabirimi kimliği. (İsteğe bağlı)  
  
 `I7`  
 Yedinci arabirimi kimliği. (İsteğe bağlı)  
  
 `I8`  
 Alt arabirimi kimliği (İsteğe bağlı)  
  
 `I9`  
 Dokuzuncu arabirimi kimliği. (İsteğe bağlı)  
  
 `flags`  
 Sınıfı için yapılandırma bayraklar. Bir veya daha fazla [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) belirtilen numaralandırmalar bir [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen arabirimleri listesinden türetilen ve QueryInterface ve GetIid için yardımcı şablonları uygular.  
  
 Her `I0` aracılığıyla `I9` arabirimi parametresi ya da IUnknown, Iınspectable, türetilmesi gerekir veya [Chainınterfaces](../windows/chaininterfaces-structure.md) şablonu. `flags` Parametre, destek IUnknown veya Iınspectable oluşturulup oluşturulmayacağını belirler.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ClassFlags`|Eşanlamlısı `RuntimeClassFlags<WinRt>`.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Implements::cancastto yöntemi](../windows/implements-cancastto-method.md)|Bir işaretçi belirtilen arabirime alır.|  
|[Implements::casttounknown yöntemi](../windows/implements-casttounknown-method.md)|İşaretçi arka plandaki IUnknown arabirimini alır.|  
|[Implements::fillarraywithıid yöntemi](../windows/implements-fillarraywithiid-method.md)|Belirtilen dizi öğesi içinde geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.|  
  
### <a name="protected-constants"></a>Korumalı sabitleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Implements::ıidcount sabiti](../windows/implements-iidcount-constant.md)|Uygulanan arabirimi kimlikleri sayısı tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)
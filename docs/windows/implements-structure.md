---
title: Uygulayan yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
dev_langs:
- C++
helpviewer_keywords:
- Implements structure
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31b95901f2c0b7ff210cc8542dce49991a9eef87
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014824"
---
# <a name="implements-structure"></a>Implements Yapısı
Implements `QueryInterface` ve `GetIid` belirtilen arabirimleri için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
  
### <a name="parameters"></a>Parametreler  
 *I0*  
 Sıfırıncı arabirim kimliği. (Zorunlu)  
  
 *I1*  
 İlk arabirim kimliği. (İsteğe bağlı)  
  
 *I2*  
 İkinci arabirim kimliği. (İsteğe bağlı)  
  
 *I3*  
 Üçüncü arabirim kimliği. (İsteğe bağlı)  
  
 *I4*  
 Dördüncü arabirim kimliği. (İsteğe bağlı)  
  
 *I5*  
 Beşinci arabirim kimliği. (İsteğe bağlı)  
  
 *I6*  
 Altıncı arabirim kimliği. (İsteğe bağlı)  
  
 *I7*  
 Yedinci arabirim kimliği. (İsteğe bağlı)  
  
 *I8*  
 Sekizinci arabirim kimliği. (İsteğe bağlı)  
  
 *I9*  
 Dokuzuncu arabirim kimliği. (İsteğe bağlı)  
  
 *bayrakları*  
 Sınıfı için yapılandırma bayraklar. Bir veya daha fazla [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) belirtilmiş numaralandırmalar bir [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen arabirimleri listesinden türetilen ve için şablonları yardımcı uygulayan `QueryInterface` ve `GetIid`.  
  
 Her *I0* aracılığıyla *I9* arabirimi parametresi öğesinden türetilmelidir `IUnknown`, `IInspectable`, veya [Chainınterfaces](../windows/chaininterfaces-structure.md) şablonu. *Bayrakları* parametre desteği için oluşturulup oluşturulmayacağını belirler `IUnknown` veya `IInspectable`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ClassFlags`|İçin bir eşanlamlı `RuntimeClassFlags<WinRt>`.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Implements::CanCastTo Metodu](../windows/implements-cancastto-method.md)|Belirtilen arabirim için bir işaretçi alır.|  
|[Implements::CastToUnknown Metodu](../windows/implements-casttounknown-method.md)|Temel alınan bir işaretçi alır `IUnknown` arabirimi.|  
|[Implements::FillArrayWithIid Metodu](../windows/implements-fillarraywithiid-method.md)|Belirtilen bir dizi öğesine geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.|  
  
### <a name="protected-constants"></a>Korumalı sabitleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Implements::IidCount Sabiti](../windows/implements-iidcount-constant.md)|Uygulanan arabirimi kimlikleri sayısını tutar.|  
  
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
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
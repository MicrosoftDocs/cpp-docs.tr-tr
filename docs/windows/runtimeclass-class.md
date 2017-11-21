---
title: "RuntimeClass sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass
dev_langs: C++
helpviewer_keywords: RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e757712b360ff3ed4de12d8236c75a691a1f0c7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclass-class"></a>RuntimeClass Sınıfı
Belirtilen sayıda arabirimleri devralır ve belirtilen Windows çalışma zamanı, klasik COM ve zayıf başvuru desteği sağlar başlatılan bir sınıfı temsil eder.  
  
 WRL türlerinden genellikle türetilen `RuntimeClass` Bu sınıf uyguladığından `AddRef`, `Release`, ve `QueryInterface`, ve modül genel başvuru sayısı yönetmeye yardımcı olur.  
  
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
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
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
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
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
  
 `classFlags`  
 Bir veya daha fazla bileşimini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değerleri.  `__WRL_CONFIGURATION_LEGACY__` Makrosu classFlags projedeki tüm çalışma zamanı sınıfları için varsayılan değeri değiştirmek için tanımlanabilir. Tanımlanmış ise, RuntimeClass Çevik olmayan GN varsayılan örnekleridir. Tanımlı değil, RuntimeClass varsayılan olarak Çevik örnekleridir. Önlemek için belirsizlik her zaman belirtmeniz RuntimeClassType::FtmBase veya RuntimeClassType::InhibitFtmBase.
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass Oluşturucusu](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass sınıfı geçerli bir örneğini başlatır.|  
|[RuntimeClass:: ~ RuntimeClass yok Edicisi](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass sınıfı, geçerli örneğini deinitializes.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `RuntimeClass`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)

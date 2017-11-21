---
title: "Modül sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module
dev_langs: C++
helpviewer_keywords: Module class
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b2536d406293d84db2ce5d5bd3e0292e0e57920e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="module-class"></a>Modül Sınıfı
İlgili nesneler koleksiyonunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template<  
   ModuleType moduleType  
>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `moduleType`  
 Bir veya daha fazla bileşimini [ModuleType](../windows/moduletype-enumeration.md) numaralandırma değerleri.  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-classes"></a>Korumalı sınıfları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier sınıfı](../windows/module-genericreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi lambda, functor veya işaretçi işlevi belirtilir.|  
|[Module::MethodReleaseNotifier sınıfı](../windows/module-methodreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi bir nesne ve kendi yöntemi için işaretçi üyesi tarafından belirtilir.|  
|[Module::ReleaseNotifier sınıfı](../windows/module-releasenotifier-class.md)|Bir modül son nesnesinde yayımlandığında, bir olay işleyiciyi çağırır.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Modül:: ~ Module yok Edicisi](../windows/module-tilde-module-destructor.md)|Modül sınıfının geçerli örneği deinitializes.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::Module Oluşturucusu](../windows/module-module-constructor.md)|Modül sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::Create yöntemi](../windows/module-create-method.md)|Bir modül bir örneğini oluşturur.|  
|[Module::DecrementObjectCount yöntemi](../windows/module-decrementobjectcount-method.md)|Nesne sayısı modül tarafından izlenen azaltır.|  
|[Module::GetActivationFactory yöntemi](../windows/module-getactivationfactory-method.md)|Modül için bir etkinleştirme üreteci alır.|  
|[Module::GetClassObject yöntemi](../windows/module-getclassobject-method.md)|Sınıf oluşturucuları önbelleği Retreives.|  
|[Module::GetModule yöntemi](../windows/module-getmodule-method.md)|Bir modül bir örneğini oluşturur.|  
|[Module::GetObjectCount yöntemi](../windows/module-getobjectcount-method.md)|Bu modülü tarafından yönetilen nesne sayısını alır.|  
|[Module::ıncrementobjectcount yöntemi](../windows/module-incrementobjectcount-method.md)|Bir modül tarafından izlenen nesne sayısını artırır.|  
|[Module::RegisterCOMObject yöntemi](../windows/module-registercomobject-method.md)|Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.|  
|[Module::RegisterObjects yöntemi](../windows/module-registerobjects-method.md)|Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.|  
|[Module::RegisterWinRTObject yöntemi](../windows/module-registerwinrtobject-method.md)|Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.|  
|[Module::Terminate yöntemi](../windows/module-terminate-method.md)|Kapatmak için modülü tarafından örneği tüm oluşturucuları neden olur.|  
|[Module::UnregisterCOMObject yöntemi](../windows/module-unregistercomobject-method.md)|Bir veya daha fazla COM nesneleri, diğer uygulamalar için bağlanmasını engelleyen kaydını siler.|  
|[Module::UnregisterObjects yöntemi](../windows/module-unregisterobjects-method.md)|Böylece diğer uygulamalar için bağlanamıyor Belirtilen modül nesneleri kaydını siler.|  
|[Module::UnregisterWinRTObject yöntemi](../windows/module-unregisterwinrtobject-method.md)|Diğer uygulamalar için bağlanamıyor böylece bir veya daha fazla Windows çalışma zamanı nesneleri kaydını siler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::Create yöntemi](../windows/module-create-method.md)|Bir modül bir örneğini oluşturur.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::objectCount_ veri üyesi](../windows/module-objectcount-data-member.md)|Kaç tane sınıfları ile oluşturulmuş izler [olun](../windows/make-function.md) işlevi.|  
|[Module::releaseNotifier_ veri üyesi](../windows/module-releasenotifier-data-member.md)|Bir işaretçi bir ReleaseNotifier nesnesine tutar.|  
  
### <a name="macros"></a>Makrolar  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|Belirtilen sınıfının bir örneğini oluşturabilirsiniz bir Fabrika içeren bir iç önbelleğe doldurur. Bu makrosu varsayılan fabrika ve grup kimliği parametreleri belirtir.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|Belirtilen sınıfının bir örneğini oluşturabilirsiniz bir Fabrika içeren bir iç önbelleğe doldurur. Bu makro belirli Fabrika parametre belirtmenize olanak sağlar.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|Belirtilen sınıfının bir örneğini oluşturabilirsiniz bir Fabrika içeren bir iç önbelleğe doldurur. Bu makro belirli Fabrika ve grup kimliği parametreleri belirtmenizi sağlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)
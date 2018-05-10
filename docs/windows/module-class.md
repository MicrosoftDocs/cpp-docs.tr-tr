---
title: Modül sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
dev_langs:
- C++
helpviewer_keywords:
- Module class
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2af8fa5bbafa76ab13f14d1a10e040a38bc6e2fb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="module-class"></a>Modül Sınıfı
İlgili nesneler koleksiyonunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template<ModuleType moduleType>  
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
|[Module::GenericReleaseNotifier Sınıfı](../windows/module-genericreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi lambda, functor veya işaretçi işlevi belirtilir.|  
|[Module::MethodReleaseNotifier Sınıfı](../windows/module-methodreleasenotifier-class.md)|Son nesne geçerli modülünde yayımlandığında, bir olay işleyiciyi çağırır. Olay işleyicisi bir nesne ve kendi yöntemi için işaretçi üyesi tarafından belirtilir.|  
|[Module::ReleaseNotifier Sınıfı](../windows/module-releasenotifier-class.md)|Bir modül son nesnesinde yayımlandığında, bir olay işleyiciyi çağırır.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::~Module Yıkıcısı](../windows/module-tilde-module-destructor.md)|Modül sınıfının geçerli örneği deinitializes.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::Module Oluşturucusu](../windows/module-module-constructor.md)|Modül sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::Create Metodu](../windows/module-create-method.md)|Bir modül bir örneğini oluşturur.|  
|[Module::DecrementObjectCount Metodu](../windows/module-decrementobjectcount-method.md)|Nesne sayısı modül tarafından izlenen azaltır.|  
|[Module::GetActivationFactory Metodu](../windows/module-getactivationfactory-method.md)|Modül için bir etkinleştirme üreteci alır.|  
|[Module::GetClassObject Metodu](../windows/module-getclassobject-method.md)|Sınıf oluşturucuları önbelleği Retreives.|  
|[Module::GetModule Metodu](../windows/module-getmodule-method.md)|Bir modül bir örneğini oluşturur.|  
|[Module::GetObjectCount Metodu](../windows/module-getobjectcount-method.md)|Bu modülü tarafından yönetilen nesne sayısını alır.|  
|[Module::IncrementObjectCount Metodu](../windows/module-incrementobjectcount-method.md)|Bir modül tarafından izlenen nesne sayısını artırır.|  
|[Module::RegisterCOMObject Metodu](../windows/module-registercomobject-method.md)|Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.|  
|[Module::RegisterObjects Metodu](../windows/module-registerobjects-method.md)|Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.|  
|[Module::RegisterWinRTObject Metodu](../windows/module-registerwinrtobject-method.md)|Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.|  
|[Module::Terminate Metodu](../windows/module-terminate-method.md)|Kapatmak için modülü tarafından örneği tüm oluşturucuları neden olur.|  
|[Module::UnregisterCOMObject Metodu](../windows/module-unregistercomobject-method.md)|Bir veya daha fazla COM nesneleri, diğer uygulamalar için bağlanmasını engelleyen kaydını siler.|  
|[Module::UnregisterObjects Metodu](../windows/module-unregisterobjects-method.md)|Böylece diğer uygulamalar için bağlanamıyor Belirtilen modül nesneleri kaydını siler.|  
|[Module::UnregisterWinRTObject Metodu](../windows/module-unregisterwinrtobject-method.md)|Diğer uygulamalar için bağlanamıyor böylece bir veya daha fazla Windows çalışma zamanı nesneleri kaydını siler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::Create Metodu](../windows/module-create-method.md)|Bir modül bir örneğini oluşturur.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Module::objectCount_ Veri Üyesi](../windows/module-objectcount-data-member.md)|Kaç tane sınıfları ile oluşturulmuş izler [olun](../windows/make-function.md) işlevi.|  
|[Module::releaseNotifier_ Veri Üyesi](../windows/module-releasenotifier-data-member.md)|Bir işaretçi bir ReleaseNotifier nesnesine tutar.|  
  
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
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
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
ms.openlocfilehash: a90a7c82706adead4379152b78d36e4dd4b91673
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416233"
---
# <a name="module-class"></a>Modül Sınıfı

İlgili nesneler koleksiyonunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>Parametreler

*moduleType*<br/>
Bir veya daha fazla birleşimi [ModuleType](../windows/moduletype-enumeration.md) sabit listesi değerleri.

## <a name="members"></a>Üyeler

### <a name="protected-classes"></a>Korumalı sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[Module::GenericReleaseNotifier Sınıfı](../windows/module-genericreleasenotifier-class.md)|Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyici lambda, functor veya işaretçi işlevi tarafından belirtilir.|
|[Module::MethodReleaseNotifier Sınıfı](../windows/module-methodreleasenotifier-class.md)|Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyicisi, bir nesne ve onun yöntemi için işaretçi üye tarafından belirtilir.|
|[Module::ReleaseNotifier Sınıfı](../windows/module-releasenotifier-class.md)|Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Module::~Module Yıkıcısı](../windows/module-tilde-module-destructor.md)|Geçerli örneğinin başlatmasını geri alır **Modülü** sınıfı.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Module::Module Oluşturucusu](../windows/module-module-constructor.md)|Yeni bir örneğini başlatır **Modülü** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Module::Create Metodu](../windows/module-create-method.md)|Bir modülün örneği oluşturur.|
|[Module::DecrementObjectCount Metodu](../windows/module-decrementobjectcount-method.md)|Nesne sayısını modülü tarafından izlenen azaltır.|
|[Module::GetActivationFactory Metodu](../windows/module-getactivationfactory-method.md)|Etkinleştirme fabrikası için modülü alır.|
|[Module::GetClassObject Metodu](../windows/module-getclassobject-method.md)|Sınıf üreteçlerini önbelleğini Retreives.|
|[Module::GetModule Metodu](../windows/module-getmodule-method.md)|Bir modülün örneği oluşturur.|
|[Module::GetObjectCount Metodu](../windows/module-getobjectcount-method.md)|Bu modülü tarafından yönetilen nesne sayısını alır.|
|[Module::IncrementObjectCount Metodu](../windows/module-incrementobjectcount-method.md)|Modül tarafından izlenen nesne sayısını artırır.|
|[Module::RegisterCOMObject Metodu](../windows/module-registercomobject-method.md)|Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.|
|[Module::RegisterObjects Metodu](../windows/module-registerobjects-method.md)|Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.|
|[Module::RegisterWinRTObject Metodu](../windows/module-registerwinrtobject-method.md)|Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.|
|[Module::Terminate Metodu](../windows/module-terminate-method.md)|Kapatmak için modülü tarafından oluşturulan tüm fabrikaları neden olur.|
|[Module::UnregisterCOMObject Metodu](../windows/module-unregistercomobject-method.md)|Bir veya daha fazla COM nesneleri, diğer uygulamalar için bağlanmasını engelleyen kaydını siler.|
|[Module::UnregisterObjects Metodu](../windows/module-unregisterobjects-method.md)|Diğer uygulamalar için bağlantı nesneleri belirtilen modüldeki kaydını siler.|
|[Module::UnregisterWinRTObject Metodu](../windows/module-unregisterwinrtobject-method.md)|Böylece diğer uygulamalar için bağlanılamıyor veya daha fazla Windows çalışma zamanı nesne kaydını siler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Module::Create Metodu](../windows/module-create-method.md)|Bir modülün örneği oluşturur.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Module::objectCount_ Veri Üyesi](../windows/module-objectcount-data-member.md)|Kaç tane sınıfları ile oluşturulmuş izler [olun](../windows/make-function.md) işlevi.|
|[Module::releaseNotifier_ Veri Üyesi](../windows/module-releasenotifier-data-member.md)|Bir işaretçi tutan bir `ReleaseNotifier` nesne.|

### <a name="macros"></a>Makrolar

|||
|-|-|
|[ActivatableClass](../windows/activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur. Bu makro, varsayılan fabrika ve grup kimliği parametreleri belirtir.|
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur. Bu makro belirli Fabrika parametresi belirlemenize olanak sağlar.|
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur. Bu makro belirli Fabrika ve grup kimliği parametreleri belirtmenizi sağlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)
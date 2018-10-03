---
title: 'Microsoft::wrl:: details Namespace | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f95eaa49db5e09bceaefafc16312250d823e5d5c
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250399"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details Ad Alanı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[ComPtrRef Sınıfı](../windows/comptrref-class.md)|ComPtr türünde bir nesne bir başvuruyu temsil eder\<T >.|
|[ComPtrRefBase Sınıfı](../windows/comptrrefbase-class.md)|Temel sınıfı temsil eder [ComPtrRef](../windows/comptrref-class.md) sınıfı.|
|[DontUseNewUseMake Sınıfı](../windows/dontusenewusemake-class.md)|İşleç engel **yeni** içinde `RuntimeClass`. Sonuç olarak, kullanmanız gereken [olun işlevi](../windows/make-function.md) yerine.|
|[EventTargetArray Sınıfı](../windows/eventtargetarray-class.md)|Olay işleyicileri dizisini temsil eder.|
|[MakeAllocator Sınıfı](../windows/makeallocator-class.md)|İle veya zayıf başvuru desteği olmayan bir etkinleştirilebilir sınıf için bellek ayırır.|
|[ModuleBase Sınıfı](../windows/modulebase-class.md)|Temel sınıfını temsil eden [Modülü](../windows/module-class.md) sınıfları.|
|[RemoveIUnknown Sınıfı](../windows/removeiunknown-class.md)|Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde sanal olmayan `QueryInterface`, `AddRef`, ve `Release` yöntemleri.|
|[WeakReference sınıfı](../windows/weakreference-class.md)|Temsil eden bir *zayıf başvuru* kullanılabilen Windows çalışma zamanı veya klasik COM ile Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ArgTraits Yapısı](../windows/argtraits-structure.md)|Belirtilen bir temsilci arabirimi ve belirtilen bir dizi parametre içeren bir anonim üye işlevini bildirir.|
|[ArgTraitsHelper Yapısı](../windows/argtraitshelper-structure.md)|Yardımcı olur, temsilci bağımsız değişkenleri genel özelliklerini tanımlayın.|
|[BoolStruct Yapısı](../windows/boolstruct-structure.md)|Tanımlar olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi. `BoolStruct` tarafından dahili olarak kullanılan [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) işleci.|
|[CreatorMap Yapısı](../windows/creatormap-structure.md)|Nesneleri kaydını başlatmak ve kaydetme hakkında bilgi içerir.|
|[DerefHelper Yapısı](../windows/derefhelper-structure.md)|Başvurusu kaldırılmış bir işaretçi temsil `T*` şablon parametresi.|
|[EnableIf Yapısı](../windows/enableif-structure.md)|İlk şablon parametresi değerlendirilirse ikinci şablon parametresi tarafından belirtilen türde bir veri üyesi tanımlar **true**.|
|[FactoryCache Yapısı](../windows/factorycache-structure.md)|Bir sınıf üreteci ve kayıtlı Windows çalışma zamanı veya COM sınıf nesnesini tanımlayan bir değer konumunu içerir.|
|[ImplementsBase Yapısı](../windows/implementsbase-structure.md)|Şablon parametre türleri doğrulamak için kullanılan [Implements yapısı](../windows/implements-structure.md).|
|[ImplementsHelper Yapısı](../windows/implementshelper-structure.md)|Uygulama yardımcı [uygular](../windows/implements-structure.md) yapısı.|
|[InterfaceList Yapısı](../windows/interfacelist-structure.md)|Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.|
|[InterfaceListHelper Yapısı](../windows/interfacelisthelper-structure.md)|Oluşturur bir `InterfaceList` yinelemeli olarak belirtilen şablon parametre bağımsız uygulama tarafından türü.|
|[InterfaceTraits Yapısı](../windows/interfacetraits-structure.md)|Genel özelliklerini bir arabirim uygular.|
|[InvokeHelper Yapısı](../windows/invokehelper-structure.md)|Bir uygulamasını sağlar `Invoke()` tabanlı yöntemini belirtilen sayı ve bağımsız değişken türü.|
|[IsBaseOfStrict Yapısı](../windows/isbaseofstrict-structure.md)|Başka bir taban bir türü olup olmadığını sınar.|
|[IsSame Yapısı](../windows/issame-structure.md)|Belirtilen türü testleri bir türü belirtilmiş olup olmadığını başka aynıdır.|
|[Nil Yapısı](../windows/nil-structure.md)|Belirtilmeyen, isteğe bağlı şablon parametre göstermek için kullanılır.|
|[RemoveReference Yapısı](../windows/removereference-structure.md)|Belirtilen sınıf şablonu parametre başvurusunu veya rvalue başvurusunu nitelik kaldırır.|
|[RuntimeClassBase Yapısı](../windows/runtimeclassbase-structure.md)|Algılamak için kullanılan `RuntimeClass` içinde [olun](../windows/make-function.md) işlevi.|
|[RuntimeClassBaseT Yapısı](../windows/runtimeclassbaset-structure.md)|İçin yardımcı yöntemleri sağlar `QueryInterface` işlemler ve başlangıç arabirim kimliği.|
|[VerifyInheritanceHelper Yapısı](../windows/verifyinheritancehelper-structure.md)|Başka bir arabirimden türetilmiş bir arabirim olup olmadığını sınar.|
|[VerifyInterfaceHelper Yapısı](../windows/verifyinterfacehelper-structure.md)|Şablon parametresi tarafından belirtilen arabirim belirli gereksinimleri karşıladığını doğrular.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[AsyncStatusInternal Sabit Listesi](../windows/asyncstatusinternal-enumeration.md)|Zaman uyumsuz işlemler durumu için iç sabit listeleri arasındaki eşlemeyi belirtir ve `Windows::Foundation::AsyncStatus` sabit listesi.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactoryCallback İşlevi](../windows/activationfactorycallback-function.md)|Belirtilen etkinleştirme kimliği için kullanılan etkinleştirme üreteci alır|
|[Move İşlevi](../windows/move-function.md)|Belirtilen bağımsız değişken bir konumdan diğerine taşır.|
|[RaiseException İşlevi](../windows/raiseexception-function.md)|Çağıran iş parçacığında bir özel durum oluşturur.|
|[Swap işlevi (WRL)](../windows/swap-function-wrl.md)|İki belirtilen bağımsız değişken değerlerini birbiriyle değiştirir.|
|[TerminateMap İşlevi](../windows/terminatemap-function.md)|Belirtilen modül sınıfı Fabrikalar kapatır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)
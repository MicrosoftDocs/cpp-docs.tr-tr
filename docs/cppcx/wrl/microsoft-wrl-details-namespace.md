---
title: Microsoft::WRL::Details Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: fce6e620600164e73d3708d98d8a7fa979e8ab42
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027490"
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
|[ComPtrRef Sınıfı](comptrref-class.md)|ComPtr türünde bir nesne bir başvuruyu temsil eder\<T >.|
|[ComPtrRefBase Sınıfı](comptrrefbase-class.md)|Temel sınıfı temsil eder [ComPtrRef](comptrref-class.md) sınıfı.|
|[DontUseNewUseMake Sınıfı](dontusenewusemake-class.md)|İşleç engel `new` içinde `RuntimeClass`. Sonuç olarak, kullanmanız gereken [olun işlevi](make-function.md) yerine.|
|[EventTargetArray Sınıfı](eventtargetarray-class.md)|Olay işleyicileri dizisini temsil eder.|
|[MakeAllocator Sınıfı](makeallocator-class.md)|İle veya zayıf başvuru desteği olmayan bir etkinleştirilebilir sınıf için bellek ayırır.|
|[ModuleBase Sınıfı](modulebase-class.md)|Temel sınıfını temsil eden [Modülü](module-class.md) sınıfları.|
|[RemoveIUnknown Sınıfı](removeiunknown-class.md)|Eşdeğer olan bir tür yapar bir `IUnknown`-tabanlı ancak türünde sanal olmayan `QueryInterface`, `AddRef`, ve `Release` yöntemleri.|
|[WeakReference Sınıfı](weakreference-class.md)|Temsil eden bir *zayıf başvuru* kullanılabilen Windows çalışma zamanı veya klasik COM ile Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ArgTraits Yapısı](argtraits-structure.md)|Belirtilen bir temsilci arabirimi ve belirtilen bir dizi parametre içeren bir anonim üye işlevini bildirir.|
|[ArgTraitsHelper Yapısı](argtraitshelper-structure.md)|Yardımcı olur, temsilci bağımsız değişkenleri genel özelliklerini tanımlayın.|
|[BoolStruct Yapısı](boolstruct-structure.md)|Tanımlar olup olmadığını bir `ComPtr` bir arabirimin nesne ömrü yönetimi. `BoolStruct` tarafından dahili olarak kullanılan [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) işleci.|
|[CreatorMap Yapısı](creatormap-structure.md)|Nesneleri kaydını başlatmak ve kaydetme hakkında bilgi içerir.|
|[DerefHelper Yapısı](derefhelper-structure.md)|Başvurusu kaldırılmış bir işaretçi temsil `T*` şablon parametresi.|
|[EnableIf Yapısı](enableif-structure.md)|İlk şablon parametresi değerlendirilirse ikinci şablon parametresi tarafından belirtilen türde bir veri üyesi tanımlar `true`.|
|[FactoryCache Yapısı](factorycache-structure.md)|Bir sınıf üreteci ve kayıtlı Windows çalışma zamanı veya COM sınıf nesnesini tanımlayan bir değer konumunu içerir.|
|[ImplementsBase Yapısı](implementsbase-structure.md)|Şablon parametre türleri doğrulamak için kullanılan [Implements yapısı](implements-structure.md).|
|[ImplementsHelper Yapısı](implementshelper-structure.md)|Uygulama yardımcı [uygular](implements-structure.md) yapısı.|
|[InterfaceList Yapısı](interfacelist-structure.md)|Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.|
|[InterfaceListHelper Yapısı](interfacelisthelper-structure.md)|Oluşturur bir `InterfaceList` yinelemeli olarak belirtilen şablon parametre bağımsız uygulama tarafından türü.|
|[InterfaceTraits Yapısı](interfacetraits-structure.md)|Genel özelliklerini bir arabirim uygular.|
|[InvokeHelper Yapısı](invokehelper-structure.md)|Bir uygulamasını sağlar `Invoke()` tabanlı yöntemini belirtilen sayı ve bağımsız değişken türü.|
|[IsBaseOfStrict Yapısı](isbaseofstrict-structure.md)|Başka bir taban bir türü olup olmadığını sınar.|
|[IsSame Yapısı](issame-structure.md)|Belirtilen türü testleri bir türü belirtilmiş olup olmadığını başka aynıdır.|
|[Nil Yapısı](nil-structure.md)|Belirtilmeyen, isteğe bağlı şablon parametre göstermek için kullanılır.|
|[RemoveReference Yapısı](removereference-structure.md)|Belirtilen sınıf şablonu parametre başvurusunu veya rvalue başvurusunu nitelik kaldırır.|
|[RuntimeClassBase Yapısı](runtimeclassbase-structure.md)|Algılamak için kullanılan `RuntimeClass` içinde [olun](make-function.md) işlevi.|
|[RuntimeClassBaseT Yapısı](runtimeclassbaset-structure.md)|İçin yardımcı yöntemleri sağlar `QueryInterface` işlemler ve başlangıç arabirim kimliği.|
|[VerifyInheritanceHelper Yapısı](verifyinheritancehelper-structure.md)|Başka bir arabirimden türetilmiş bir arabirim olup olmadığını sınar.|
|[VerifyInterfaceHelper Yapısı](verifyinterfacehelper-structure.md)|Şablon parametresi tarafından belirtilen arabirim belirli gereksinimleri karşıladığını doğrular.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[AsyncStatusInternal Sabit Listesi](asyncstatusinternal-enumeration.md)|Zaman uyumsuz işlemler durumu için iç sabit listeleri arasındaki eşlemeyi belirtir ve `Windows::Foundation::AsyncStatus` sabit listesi.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactoryCallback İşlevi](activationfactorycallback-function.md)|Belirtilen etkinleştirme kimliği için kullanılan etkinleştirme üreteci alır|
|[Move İşlevi](move-function.md)|Belirtilen bağımsız değişken bir konumdan diğerine taşır.|
|[RaiseException İşlevi](raiseexception-function.md)|Çağıran iş parçacığında bir özel durum oluşturur.|
|[Swap İşlevi (WRL)](swap-function-wrl.md)|İki belirtilen bağımsız değişken değerlerini birbiriyle değiştirir.|
|[TerminateMap İşlevi](terminatemap-function.md)|Belirtilen modül sınıfı Fabrikalar kapatır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)
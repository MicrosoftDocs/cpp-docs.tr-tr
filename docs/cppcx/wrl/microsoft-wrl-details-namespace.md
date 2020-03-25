---
title: Microsoft::WRL::Details Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: 4e8d2e5a2c7e6655674c4e965cd7222d930dff9a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213791"
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
|[ComPtrRef Sınıfı](comptrref-class.md)|ComPtr\<T > türünde bir nesne başvurusunu temsil eder.|
|[ComPtrRefBase Sınıfı](comptrrefbase-class.md)|[ComPtrRef](comptrref-class.md) sınıfının temel sınıfını temsil eder.|
|[DontUseNewUseMake Sınıfı](dontusenewusemake-class.md)|`RuntimeClass`işlecinin `new` kullanımını engeller. Sonuç olarak, bunun yerine [Make işlevini](make-function.md) kullanmanız gerekir.|
|[EventTargetArray Sınıfı](eventtargetarray-class.md)|Bir olay işleyicileri dizisini temsil eder.|
|[MakeAllocator Sınıfı](makeallocator-class.md)|Zayıf başvuru desteği olan veya olmayan bir etkinleştirilebilir sınıfı için bellek ayırır.|
|[ModuleBase Sınıfı](modulebase-class.md)|[Modül](module-class.md) sınıflarının taban sınıfını temsil eder.|
|[RemoveIUnknown Sınıfı](removeiunknown-class.md)|`IUnknown`tabanlı bir türe eşdeğer, ancak sanal olmayan `QueryInterface`, `AddRef`ve `Release` yöntemlerine sahip bir tür yapar.|
|[WeakReference Sınıfı](weakreference-class.md)|Windows Çalışma Zamanı veya klasik COM ile kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ArgTraits Yapısı](argtraits-structure.md)|Belirtilen bir temsilci arabirimi ve belirtilen sayıda parametreye sahip anonim bir üye işlevi bildirir.|
|[ArgTraitsHelper Yapısı](argtraitshelper-structure.md)|Temsilci bağımsız değişkenlerinin ortak özelliklerini tanımlamaya yardımcı olur.|
|[BoolStruct Yapısı](boolstruct-structure.md)|Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini tanımlar. `BoolStruct`, [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) işleci tarafından dahili olarak kullanılır.|
|[CreatorMap Yapısı](creatormap-structure.md)|Nesneleri başlatma, kaydetme ve kaydını silme hakkında bilgiler içerir.|
|[DerefHelper Yapısı](derefhelper-structure.md)|`T*` Template parametresine başvuru yapılan bir işaretçiyi temsil eder.|
|[EnableIf Yapısı](enableif-structure.md)|İlk şablon parametresi `true`olarak değerlendirilirse ikinci şablon parametresi tarafından belirtilen türün veri üyesini tanımlar.|
|[FactoryCache Yapısı](factorycache-structure.md)|Bir sınıf fabrikasının konumunu ve kayıtlı bir Windows Çalışma Zamanı ya da COM sınıfı nesnesini tanımlayan bir değeri içerir.|
|[ImplementsBase Yapısı](implementsbase-structure.md)|[Uygulayan yapıda](implements-structure.md)şablon parametre türlerini doğrulamak için kullanılır.|
|[ImplementsHelper Yapısı](implementshelper-structure.md)|, [Uygulayan](implements-structure.md) yapıyı uygulamaya yardımcı olur.|
|[InterfaceList Yapısı](interfacelist-structure.md)|Bir arabirim özyinelemeli listesini oluşturmak için kullanılır.|
|[InterfaceListHelper Yapısı](interfacelisthelper-structure.md)|Belirtilen şablon parametresi bağımsız değişkenlerini yinelemeli olarak uygulayarak bir `InterfaceList` türü oluşturur.|
|[InterfaceTraits Yapısı](interfacetraits-structure.md)|Bir arabirimin ortak karakteristiklerini uygular.|
|[InvokeHelper Yapısı](invokehelper-structure.md)|`Invoke()` yönteminin, belirtilen sayı ve bağımsız değişken türüne göre uygulanmasını sağlar.|
|[IsBaseOfStrict Yapısı](isbaseofstrict-structure.md)|Bir türün diğerinin temeli olup olmadığını test eder.|
|[IsSame Yapısı](issame-structure.md)|Belirtilen bir türün, belirtilen başka bir türle aynı olup olmadığını test eder.|
|[Nil Yapısı](nil-structure.md)|Belirtilmeyen, isteğe bağlı bir şablon parametresini göstermek için kullanılır.|
|[RemoveReference Yapısı](removereference-structure.md)|Belirtilen sınıf şablonu parametresinden başvuruyu veya rvalue-Reference nitelik öğesini şeritler.|
|[RuntimeClassBase Yapısı](runtimeclassbase-structure.md)|[Make](make-function.md) işlevindeki `RuntimeClass` algılamak için kullanılır.|
|[RuntimeClassBaseT Yapısı](runtimeclassbaset-structure.md)|`QueryInterface` işlemler ve arabirim kimliklerini almak için yardımcı yöntemler sağlar.|
|[VerifyInheritanceHelper Yapısı](verifyinheritancehelper-structure.md)|Bir arabirimin başka bir arabirimden türetilip türetilmediğini sınar.|
|[VerifyInterfaceHelper Yapısı](verifyinterfacehelper-structure.md)|Şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.|

### <a name="enumerations"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[AsyncStatusInternal Sabit Listesi](asyncstatusinternal-enumeration.md)|Zaman uyumsuz işlemlerin durumu ve `Windows::Foundation::AsyncStatus` numaralandırması arasındaki iç numaralandırmalar arasındaki eşlemeyi belirtir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactoryCallback İşlevi](activationfactorycallback-function.md)|Belirtilen etkinleştirme KIMLIĞI için etkinleştirme fabrikasını alır.|
|[Move İşlevi](move-function.md)|Belirtilen bağımsız değişkeni bir konumdan diğerine kaydırır.|
|[RaiseException İşlevi](raiseexception-function.md)|Çağıran iş parçacığında bir özel durum oluşturur.|
|[Swap İşlevi (WRL)](swap-function-wrl.md)|Belirtilen iki bağımsız değişkenin değerlerini değiş tokuş eder.|
|[TerminateMap İşlevi](terminatemap-function.md)|Belirtilen modüldeki sınıf fabrikalarını kapatır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h, Client. h, corewrapper. h, Event. h, FTM. h, Implements. h, iç. h, modül. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)

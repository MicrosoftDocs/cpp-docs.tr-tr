---
description: 'Hakkında daha fazla bilgi edinin: Microsoft:: WRL::D euçlar ad alanı'
title: Microsoft::WRL::Details Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: c82d7389c80d35aa041dccc7c6bc8d202fba9c29
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195118"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details Ad Alanı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[ComPtrRef sınıfı](comptrref-class.md)|ComPtr türünde bir nesnenin başvurusunu temsil eder \<T> .|
|[ComPtrRefBase sınıfı](comptrrefbase-class.md)|[ComPtrRef](comptrref-class.md) sınıfının temel sınıfını temsil eder.|
|[DontUseNewUseMake sınıfı](dontusenewusemake-class.md)|İçindeki işlecinin kullanımını `new` engeller `RuntimeClass` . Sonuç olarak, bunun yerine [Make işlevini](make-function.md) kullanmanız gerekir.|
|[EventTargetArray Sınıfı](eventtargetarray-class.md)|Bir olay işleyicileri dizisini temsil eder.|
|[Makeayırıcı sınıfı](makeallocator-class.md)|Zayıf başvuru desteği olan veya olmayan bir etkinleştirilebilir sınıfı için bellek ayırır.|
|[ModuleBase sınıfı](modulebase-class.md)|[Modül](module-class.md) sınıflarının taban sınıfını temsil eder.|
|[RemoveIUnknown Sınıfı](removeiunknown-class.md)|, `IUnknown` Tabanlı bir türe eşdeğer, ancak sanal olmayan `QueryInterface` , `AddRef` ve yöntemlere sahip bir tür yapar `Release` .|
|[WeakReference sınıfı](weakreference-class.md)|Windows Çalışma Zamanı veya klasik COM ile kullanılabilen *zayıf bir başvuruyu* temsil eder. Zayıf başvuru, erişilebilir olabilecek veya erişilemeyen bir nesneyi temsil eder.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[ArgTraits Yapısı](argtraits-structure.md)|Belirtilen bir temsilci arabirimi ve belirtilen sayıda parametreye sahip anonim bir üye işlevi bildirir.|
|[ArgTraitsHelper Yapısı](argtraitshelper-structure.md)|Temsilci bağımsız değişkenlerinin ortak özelliklerini tanımlamaya yardımcı olur.|
|[BoolStruct Yapısı](boolstruct-structure.md)|Bir `ComPtr` arabirimin nesne ömrünü yönetip yönetmediğini tanımlar. `BoolStruct` , [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) işleci tarafından dahili olarak kullanılır.|
|[CreatorMap Yapısı](creatormap-structure.md)|Nesneleri başlatma, kaydetme ve kaydını silme hakkında bilgiler içerir.|
|[DerefHelper Yapısı](derefhelper-structure.md)|Şablon parametresine başvuru yapılan bir işaretçiyi temsil eder `T*` .|
|[EnableIf Yapısı](enableif-structure.md)|İlk şablon parametresi olarak değerlendirilirse ikinci şablon parametresi tarafından belirtilen türün veri üyesini tanımlar **`true`** .|
|[FactoryCache Yapısı](factorycache-structure.md)|Bir sınıf fabrikasının konumunu ve kayıtlı bir Windows Çalışma Zamanı ya da COM sınıfı nesnesini tanımlayan bir değeri içerir.|
|[ImplementsBase Yapısı](implementsbase-structure.md)|[Uygulayan yapıda](implements-structure.md)şablon parametre türlerini doğrulamak için kullanılır.|
|[ImplementsHelper Yapısı](implementshelper-structure.md)|, [Uygulayan](implements-structure.md) yapıyı uygulamaya yardımcı olur.|
|[InterfaceList Yapısı](interfacelist-structure.md)|Bir arabirim özyinelemeli listesini oluşturmak için kullanılır.|
|[InterfaceListHelper Yapısı](interfacelisthelper-structure.md)|`InterfaceList`Belirtilen şablon parametresi bağımsız değişkenlerini yinelemeli olarak uygulayarak bir tür oluşturur.|
|[InterfaceTraits Yapısı](interfacetraits-structure.md)|Bir arabirimin ortak karakteristiklerini uygular.|
|[InvokeHelper Yapısı](invokehelper-structure.md)|`Invoke()`Yöntemin, belirtilen sayı ve bağımsız değişken türüne göre bir uygulamasını sağlar.|
|[IsBaseOfStrict Yapısı](isbaseofstrict-structure.md)|Bir türün diğerinin temeli olup olmadığını test eder.|
|[IsSame Yapısı](issame-structure.md)|Belirtilen bir türün, belirtilen başka bir türle aynı olup olmadığını test eder.|
|[Nil Yapısı](nil-structure.md)|Belirtilmeyen, isteğe bağlı bir şablon parametresini göstermek için kullanılır.|
|[RemoveReference Yapısı](removereference-structure.md)|Belirtilen sınıf şablonu parametresinden başvuruyu veya rvalue-Reference nitelik öğesini şeritler.|
|[RuntimeClassBase Yapısı](runtimeclassbase-structure.md)|`RuntimeClass` [Make](make-function.md) işlevinde algılamak için kullanılır.|
|[RuntimeClassBaseT Yapısı](runtimeclassbaset-structure.md)|İşlemler için yardımcı yöntemler sağlar `QueryInterface` ve arabirim kimliklerini elde edin.|
|[VerifyInheritanceHelper Yapısı](verifyinheritancehelper-structure.md)|Bir arabirimin başka bir arabirimden türetilip türetilmediğini sınar.|
|[VerifyInterfaceHelper Yapısı](verifyinterfacehelper-structure.md)|Şablon parametresi tarafından belirtilen arabirimin belirli gereksinimleri karşıladığını doğrular.|

### <a name="enumerations"></a>Listelemeler

|Ad|Açıklama|
|----------|-----------------|
|[AsyncStatusInternal Sabit Listesi](asyncstatusinternal-enumeration.md)|Zaman uyumsuz işlemlerin ve numaralandırmanın durumunun iç numaralandırmalar arasındaki eşlemeyi belirtir `Windows::Foundation::AsyncStatus` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[ActivationFactoryCallback Işlevi](activationfactorycallback-function.md)|Belirtilen etkinleştirme KIMLIĞI için etkinleştirme fabrikasını alır.|
|[Move Işlevi](move-function.md)|Belirtilen bağımsız değişkeni bir konumdan diğerine kaydırır.|
|[RaiseException Işlevi](raiseexception-function.md)|Çağıran iş parçacığında bir özel durum oluşturur.|
|[Swap Işlevi (WRL)](swap-function-wrl.md)|Belirtilen iki bağımsız değişkenin değerlerini değiş tokuş eder.|
|[TerminateMap Işlevi](terminatemap-function.md)|Belirtilen modüldeki sınıf fabrikalarını kapatır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h, Client. h, corewrapper. h, Event. h, FTM. h, Implements. h, iç. h, modül. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)<br/>
[Microsoft:: WRL:: sarmalayıcılar ad alanı](microsoft-wrl-wrappers-namespace.md)

---
title: IThreadProxy Yapısı
ms.date: 11/04/2016
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
ms.openlocfilehash: fc2fb2df06225a5c963fe39178c1b4a10f77953d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368135"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy Yapısı

Yürütme iş parçacığı için bir soyutlama. Oluşturduğunuz zamanlayıcının `SchedulerType` ilke anahtarına bağlı olarak, Kaynak Yöneticisi size normal bir Win32 iş parçacığı veya kullanıcı modu zamanlanabilir (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy'si verir. UMS iş parçacıkları, Windows 7 ve üzeri sürümlere sahip 64 bit işletim sistemlerinde desteklenir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IThreadProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IThreadProxy::Getid](#getid)|İş parçacığı proxy'si için benzersiz bir tanımlayıcı döndürür.|
|[IThreadProxy::SwitchOut](#switchout)|Bağlamı temel sanal işlemci kökünden ayırır.|
|[IThreadProxy::Switchto](#switchto)|Şu anda yürütülen bağlamdan farklı bir bağlamaya bir işbirliği bağlam anahtarı gerçekleştirir.|
|[IThreadProxy::yieldtosystem](#yieldtosystem)|Arama iş parçacığının geçerli işlemcide çalışmaya hazır başka bir iş parçacığına yürütme verimi almasına neden olur. İşletim sistemi yürütülecek sonraki iş parçacığı seçer.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı vekilleri, iş gönderme aracı olarak `IExecutionContext` arabirim tarafından temsil edilen yürütme bağlamları ile birleştiğinde.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="ithreadproxygetid-method"></a><a name="getid"></a>IThreadProxy::GetId Yöntemi

İş parçacığı proxy'si için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

## <a name="ithreadproxyswitchout-method"></a><a name="switchout"></a>IThreadProxy::SwitchOut Yöntemi

Bağlamı temel sanal işlemci kökünden ayırır.

```cpp
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>Parametreler

*switchState*<br/>
Anahtarı çalıştıran iş parçacığı proxy'sinin durumunu gösterir. Parametre türündedir. `SwitchingProxyState`

### <a name="remarks"></a>Açıklamalar

Herhangi `SwitchOut` bir nedenle, bir bağlamı yürütüldettiği sanal işlemci kökünden ayırmanız gerekiyorsa kullanın. Parametreye `switchState`geçtiğiniz değere ve sanal işlemci kökünde yürütülüp yürütülmediğine bağlı olarak, arama hemen döndürülecek veya bağlamla ilişkili iş parçacığı proxy'sini engeller. Parametre olarak ayarlanmış `SwitchOut` bir `Idle`hatadır. Bunu yapmak [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum la sonuçlanır.

`SwitchOut`zamanlayıcınızın sahip olduğu sanal işlemci köklerinin sayısını azaltmak istediğinizde, kaynak yöneticisi bunu yapmanız için talimat verdiği nden veya geçici olarak aşırı abone olan bir sanal işlemci kökü istediğinizden ve bu sistemle birlikte yaptığınızdan yararlı dır. Bu durumda, parametre `switchState` ayarlanmış bir arama `Blocking` `SwitchOut` yapmadan önce, iVirtualProcessorRoot yöntemini çağırmalısınız::Sanal işlemci kökünde [kaldırın.](iexecutionresource-structure.md#remove) Bu iş parçacığı proxy engelleyecek ve zamanlayıcı farklı bir sanal işlemci kökü yürütmek için kullanılabilir olduğunda yürütme devam edecektir. Engelleme iş parçacığı proxy bu iş parçacığı `SwitchTo` proxy yürütme bağlamına geçmek için işlev çağırarak devam edilebilir. Sanal işlemci kökünü etkinleştirmek için ilişkili bağlamını kullanarak iş parçacığı proxy'sini de devam ettirebilirsiniz. Bunun nasıl yapılacılaştırılaçılabildiğim hakkında daha fazla bilgi [iVirtualProcessorRoot::Etkinle.](ivirtualprocessorroot-structure.md#activate)

`SwitchOut`iş parçacığı proxy'sini engellerken veya üzerinde çalıştığı sanal işlemci kökünden ve iş gönderdiği zamanlayıcıdan geçici olarak ayırırken gelecekte etkinleştirilebilecek sanal işlemciyi yeniden başlatmayı istediğinizde de kullanılabilir. İş `SwitchOut` parçacığı proxy `switchState` engellemek `Blocking` istiyorsanız parametre kümesi ile kullanın. Daha sonra ya da `SwitchTo` `IVirtualProcessorRoot::Activate` yukarıda belirtildiği gibi kullanarak devam edilebilir. Bu `SwitchOut` iş parçacığı proxy'sini üzerinde çalışan sanal işlemci kökünden ve sanal işlemcinin ilişkili olduğu zamanlayıcıdan geçici olarak ayırmak `Nesting` istediğinizde ayarlanan parametreyi kullanın. Sanal `SwitchOut` işlemci kökünde `switchState` `Nesting` yürütülderken ayarlanan parametreyle arama yapmak, kökün yeniden başlatılmasına ve geçerli iş parçacığı proxy'sinin buna gerek kalmadan yürütmeye devam etmesine neden olur. İş parçacığı proxy ithreadproxy çağıran kadar zamanlayıcı bırakmış olarak kabul [edilir::SwitchOut](#switchout) yöntemi zaman içinde daha sonraki bir noktada ile. `Blocking` Parametre ayarlı ikinci `SwitchOut` çağrı, `Blocking` bağlandığı zamanlayıcı `SwitchTo` tarafından veya `IVirtualProcessorRoot::Activate` ayrıldığı zamanlayıcıda sürdürülebilmek için bağlamı engellenmiş bir duruma döndürmek için tasarlanmıştır. Sanal işlemci kökünde yürütülmediği için yeniden başlatma gerçekleşmez.

Yeniden başlatılan sanal işlemci kökü, zamanlayıcınızın Kaynak Yöneticisi tarafından verilmiş yepyeni bir sanal işlemci kökünden farklı değildir. Bir yürütme bağlamı ile etkinleştirerek yürütme için `IVirtualProcessorRoot::Activate`kullanabilirsiniz.

`SwitchOut`şu anda `IThreadProxy` çalıştırılan iş parçacığı temsil eden arabirim de çağrılması gerekir veya sonuçlar tanımsız.

Visual Studio 2010 ile gönderilen kitaplıklarda ve üstbilgilere göre bu yöntem bir parametre almadı ve sanal işlemci kökünü yeniden başlatmadı. Eski davranışı korumak için varsayılan parametre değeri `Blocking` sağlanır.

## <a name="ithreadproxyswitchto-method"></a><a name="switchto"></a>IThreadProxy::SwitchTo Yöntemi

Şu anda yürütülen bağlamdan farklı bir bağlamaya bir işbirliği bağlam anahtarı gerçekleştirir.

```cpp
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```

### <a name="parameters"></a>Parametreler

*Pcontext*<br/>
Yürütme bağlamında işbirliği içinde geçmek için.

*switchState*<br/>
Anahtarı çalıştıran iş parçacığı proxy'sinin durumunu gösterir. Parametre türündedir. `SwitchingProxyState`

### <a name="remarks"></a>Açıklamalar

Bir yürütme bağlamından diğerine, [IExecutionContext::Dispatch](iexecutioncontext-structure.md#dispatch) yöntemiilk yürütme bağlamından geçmek için bu yöntemi kullanın. Yöntem, zaten bir `pContext` tanesiyle ilişkili değilse yürütme bağlamını bir iş parçacığı proxy'si ile ilişkilendirer. Geçerli iş parçacığı proxy'sinin sahipliği, bağımsız değişken `switchState` için belirttiğiniz değere göre belirlenir.

Şu anda çalıştırılamakta olan iş parçacığı proxy'sini Kaynak Yöneticisi'ne döndürmek istediğinizde değeri `Idle` kullanın. Parametre `SwitchTo` `switchState` ayarlı arama, yürütme bağlamınında `Idle` `pContext` temel yürütme kaynağında yürütmeye başlamasına neden olur. Bu iş parçacığı proxy'sinin sahipliği Kaynak Yöneticisi'ne aktarılır ve aktarım `Dispatch` işlemini `SwitchTo` tamamlamak için iadelerden kısa bir süre sonra yürütme bağlamının yönteminden dönmeniz beklenir. İş parçacığı proxy'sinin gönderdiği yürütme bağlamı iş parçacığı proxy'sinden kesilir ve zamanlayıcı onu yeniden kullanmak veya uygun gördüğü şekilde yok etmek için özgürdür.

Bu iş `Blocking` parçacığı proxy engellenen bir durum girmek istediğinizde değeri kullanın. Parametre `SwitchTo` `switchState` ayarlı arama `Blocking` yürütme bağlamı `pContext` yürütme başlatmak için neden olur ve devam edene kadar geçerli iş parçacığı proxy engelleyin. İş parçacığı proxy `Blocking` durumda olduğunda zamanlayıcı iş parçacığı proxy sahipliğini korur. Engelleme iş parçacığı proxy bu iş parçacığı `SwitchTo` proxy yürütme bağlamına geçmek için işlev çağırarak devam edilebilir. Sanal işlemci kökünü etkinleştirmek için ilişkili bağlamını kullanarak iş parçacığı proxy'sini de devam ettirebilirsiniz. Bunun nasıl yapılacılaştırılaçılabildiğim hakkında daha fazla bilgi [iVirtualProcessorRoot::Etkinle.](ivirtualprocessorroot-structure.md#activate)

Bu iş `Nesting` parçacığı proxy'sini üzerinde çalıştığı sanal işlemci kökünden ve iş gönderdiği zamanlayıcıdan geçici olarak ayırmak istediğinizde değeri kullanın. Parametre `SwitchTo` `switchState` ile çağrı `Nesting` yürütme bağlamı `pContext` yürütme başlatmak için neden olur ve geçerli iş parçacığı proxy de sanal bir işlemci kökü gerek kalmadan yürütme devam ediyor. İş parçacığı proxy ithreadproxy çağıran kadar zamanlayıcı bırakmış olarak kabul [edilir::SwitchOut](#switchout) yöntemi zaman içinde daha sonraki bir noktada. Yöntem, `IThreadProxy::SwitchOut` yeniden zamanlamak için sanal bir işlemci kökü kullanılabilir olana kadar iş parçacığı proxy'sini engelleyebilir.

`SwitchTo`şu anda `IThreadProxy` çalıştırılan iş parçacığı temsil eden arabirim de çağrılması gerekir veya sonuçlar tanımsız. Parametre `invalid_argument` `pContext` ' ye `NULL`ayarlanırsa işlev atar.

## <a name="ithreadproxyyieldtosystem-method"></a><a name="yieldtosystem"></a>IThreadProxy::yieldtosystem yöntemi

Arama iş parçacığının geçerli işlemcide çalışmaya hazır başka bir iş parçacığına yürütme verimi almasına neden olur. İşletim sistemi yürütülecek sonraki iş parçacığı seçer.

```cpp
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>Açıklamalar

Normal bir Windows iş parçacığı tarafından desteklenen `YieldToSystem` bir iş parçacığı proxy `SwitchToThread`tarafından çağrıldığında, tam olarak Windows işlevi gibi çalışır. Ancak, kullanıcı modu zamanlanabilir (UMS) iş parçacığı `SwitchToThread` çağrıldığında, işlev, işletim sistemi yerine kullanıcı modu zamanlayıcısıçalıştırmak için bir sonraki iş parçacığı seçme görevi temsilci. Sistemde farklı bir hazır iş parçacığına geçiş in `YieldToSystem`istenilen etkiyi elde etmek için kullanın.

`YieldToSystem`şu anda `IThreadProxy` çalıştırılan iş parçacığı temsil eden arabirim de çağrılması gerekir veya sonuçlar tanımsız.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IExecutionContext Yapısı](iexecutioncontext-structure.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)

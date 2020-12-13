---
description: ': IThreadProxy yapısı hakkında daha fazla bilgi edinin'
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
ms.openlocfilehash: e63a4d2bc29a1ae846e30d1b7e93c125def971b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334385"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy Yapısı

Yürütmenin iş parçacığı için bir soyutlama. `SchedulerType`Oluşturduğunuz Scheduler ilke anahtarına bağlı olarak Kaynak Yöneticisi, size düzenli bir Win32 iş parçacığı veya Kullanıcı modu zamanlanabilen (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy 'si verir. UMS iş parçacıkları, Windows 7 ve üzeri sürümleri ile 64 bit işletim sistemlerinde desteklenir.

## <a name="syntax"></a>Syntax

```cpp
struct IThreadProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IThreadProxy:: GetId](#getid)|İş parçacığı proxy 'si için benzersiz bir tanımlayıcı döndürür.|
|[IThreadProxy:: geçiş](#switchout)|Bağlamı temeldeki sanal işlemci kökünden ilişkilendirir.|
|[IThreadProxy:: SwitchTo](#switchto)|Şu anda yürütülmekte olan bağlamdan farklı bir içerik anahtarı gerçekleştirir.|
|[IThreadProxy:: Ödemedtosystem](#yieldtosystem)|Çağıran iş parçacığının, geçerli işlemcide çalıştırılmaya HAZIRAN başka bir iş parçacığına yürütülmesini sağlar. İşletim sistemi yürütülecek bir sonraki iş parçacığını seçer.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı proxy 'leri, `IExecutionContext` iş gönderme yöntemi olarak arabirim tarafından temsil edilen yürütme bağlamlarına bağlıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="ithreadproxygetid-method"></a><a name="getid"></a> IThreadProxy:: GetID Yöntemi

İş parçacığı proxy 'si için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

## <a name="ithreadproxyswitchout-method"></a><a name="switchout"></a> IThreadProxy:: geçiş yöntemi

Bağlamı temeldeki sanal işlemci kökünden ilişkilendirir.

```cpp
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>Parametreler

*switchState*<br/>
Anahtarı yürüten iş parçacığı proxy 'sinin durumunu gösterir. Parametresi türündedir `SwitchingProxyState` .

### <a name="remarks"></a>Açıklamalar

`SwitchOut`Herhangi bir nedenle, bir bağlamın üzerinde yürütüldüğü sanal işlemci köküyle ilişkisini kaldırmak gerekirse kullanın. Parametreye geçirdiğiniz değere `switchState` ve sanal bir işlemci kökünde yürütme yapılıp yapılmayacağını bağlı olarak, çağrı hemen döndürülür ya da bağlamla ilişkili iş parçacığı proxy 'sini engeller. `SwitchOut`Olarak ayarlanan parametre ile çağırma bir hatadır `Idle` . Bunu yapmak [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel duruma neden olur.

`SwitchOut` Scheduler 'ın sahip olduğu sanal işlemci köklerinin sayısını azaltmak istediğinizde, Kaynak Yöneticisi bunu sizin yapmanız istendiğinden veya geçici olarak kullanılabilir bir sanal işlemci kökü isteğiniz ve bununla birlikte yapıldığından faydalıdır. Bu durumda, olarak ayarlanmış parametresi ile öğesine çağrı yapmadan önce sanal işlemci kökünde [IVirtualProcessorRoot:: Remove](iexecutionresource-structure.md#remove) yöntemini çağırmanız gerekir `SwitchOut` `switchState` `Blocking` . Bu işlem, iş parçacığı proxy 'sini engeller ve Scheduler 'da farklı bir sanal işlemci kökü yürütmek için kullanılabilir olduğunda yürütmeyi sürdürür. Engelleyici iş parçacığı proxy 'si, `SwitchTo` Bu iş parçacığı proxy 'sinin yürütme bağlamına geçiş yapmak için işlevi çağırarak devam edebilir. Ayrıca, bir sanal işlemci kökünü etkinleştirmek için ilişkili bağlamını kullanarak iş parçacığı proxy 'sini de sürdürebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate).

`SwitchOut` , sanal işlemciyi yeniden başlatmak istediğinizde de kullanılabilir, böylece iş parçacığı proxy 'sini engelliyor veya üzerinde çalıştığı sanal işlemci kökünden geçici olarak bir süre önce ve bu işlem için iş Gönderen Zamanlayıcı tarafından etkinleştirilebilir. `SwitchOut` `switchState` İş parçacığı proxy 'sini engellemek istiyorsanız, parametresiyle birlikte kullanın `Blocking` . Daha sonra, `SwitchTo` yukarıda belirtildiği gibi veya kullanılarak devam edilebilir `IVirtualProcessorRoot::Activate` . `SwitchOut` `Nesting` Bu iş parçacığı proxy 'sini, üzerinde çalıştığı sanal işlemci kökünden ve Sanal işlemcinin ilişkilendirildiği Scheduler 'dan geçici olarak ayırmak istediğinizde, olarak ayarlanmış parametresiyle kullanın. `SwitchOut` `switchState` Bir sanal işlemci kökünde yürütülürken olarak ayarlanan parametresi ile çağırmak, `Nesting` kökün yeniden başlatılmasına ve geçerli iş parçacığı proxy 'sinin bir tane gerekmeden yürütmeye devam etmesine neden olur. İş parçacığı proxy 'si, daha sonraki bir zamanda ile [IThreadProxy:: sıchout](#switchout) yöntemini çağırana kadar Scheduler 'ı bıraktı olarak kabul edilir `Blocking` . `SwitchOut`Parametresi olarak ayarlanan ikinci çağrı, `Blocking` bağlamı engellenen bir duruma döndürmeye yöneliktir, böylelikle `SwitchTo` veya bağlantısı `IVirtualProcessorRoot::Activate` kesilen zamanlayıcıda devam ettirilebilecek. Sanal işlemci kökünde yürütülmediği için yeniden başlatma gerçekleşmez.

Yeniden başlatılan bir sanal işlemci kökü, Scheduler 'ın Kaynak Yöneticisi tarafından verildiği yeni bir sanal işlemci kökünden farklı değildir. Öğesini kullanarak bir yürütme bağlamı etkinleştirerek, yürütme için kullanabilirsiniz `IVirtualProcessorRoot::Activate` .

`SwitchOut``IThreadProxy`Şu anda yürütülmekte olan iş parçacığını temsil eden arabirim üzerinde çağrılmalıdır veya sonuçlar tanımsız.

Visual Studio 2010 ile birlikte gelen kitaplıklarda ve üstbilgilere bu yöntem bir parametre almadı ve sanal işlemci kökünü yeniden göndermedi. Eski davranışı korumak için varsayılan parametre değeri `Blocking` sağlanır.

## <a name="ithreadproxyswitchto-method"></a><a name="switchto"></a> IThreadProxy:: SwitchTo yöntemi

Şu anda yürütülmekte olan bağlamdan farklı bir içerik anahtarı gerçekleştirir.

```cpp
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```

### <a name="parameters"></a>Parametreler

*pContext*<br/>
Birlikte kullanılacak yürütme bağlamı.

*switchState*<br/>
Anahtarı yürüten iş parçacığı proxy 'sinin durumunu gösterir. Parametresi türündedir `SwitchingProxyState` .

### <a name="remarks"></a>Açıklamalar

İlk yürütme bağlamının [IExecutionContext::D ispatch](iexecutioncontext-structure.md#dispatch) yönteminden bir yürütme bağlamından diğerine geçiş yapmak için bu yöntemi kullanın. Yöntemi, `pContext` zaten bir ilişkili değilse, yürütme bağlamını bir iş parçacığı proxy 'si ile ilişkilendirir. Geçerli iş parçacığı proxy 'sinin sahipliği, bağımsız değişkeni için belirttiğiniz değere göre belirlenir `switchState` .

`Idle`Şu anda yürütülmekte olan iş parçacığı proxy 'sini Kaynak Yöneticisi döndürmek istediğinizde değeri kullanın. `SwitchTo`Parametresi `switchState` olarak ayarlanan ile çağırmak, `Idle` yürütme bağlamının `pContext` temel yürütme kaynağında yürütülmeye başlamasına neden olur. Bu iş parçacığı proxy 'sinin sahipliği Kaynak Yöneticisi aktarılır ve `Dispatch` `SwitchTo` Aktarım işleminin tamamlanabilmesi için, geri dönüşten sonra yürütme bağlamı yönteminden geri dönebilmeniz beklenmektedir. İş parçacığı proxy 'sinin gönderildiği yürütme bağlamı, iş parçacığı proxy 'sinden ilişkisi kesildi ve Zamanlayıcı onu yeniden kullanmak veya uygun gördüğü sürece yok etmek için ücretsizdir.

`Blocking`Bu iş parçacığı proxy 'sinin engellenen bir durum girmesini istediğinizde değeri kullanın. `SwitchTo`Parametresi `switchState` olarak ayarlanan ile çağırmak `Blocking` , yürütme bağlamının yürütülmeye başlamasına neden olur `pContext` ve devam edene kadar geçerli iş parçacığı proxy 'sini engeller. Zamanlayıcı, iş parçacığı proxy 'si durumundayken iş parçacığı proxy 'sinin sahipliğini korur `Blocking` . Engelleyici iş parçacığı proxy 'si, `SwitchTo` Bu iş parçacığı proxy 'sinin yürütme bağlamına geçiş yapmak için işlevi çağırarak devam edebilir. Ayrıca, bir sanal işlemci kökünü etkinleştirmek için ilişkili bağlamını kullanarak iş parçacığı proxy 'sini de sürdürebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate).

`Nesting`Bu iş parçacığı proxy 'sini, üzerinde çalıştığı sanal işlemci kökünden ve için iş Gönderen Scheduler 'dan geçici olarak ayırmak istediğinizde değeri kullanın. `SwitchTo`Parametresi `switchState` olarak ayarlanan ile çağırmak, `Nesting` yürütme bağlamının yürütülmeye başlamasına neden olur `pContext` ve geçerli iş parçacığı proxy 'si, sanal işlemci köküne gerek olmadan yürütmeye devam eder. İş parçacığı proxy 'si, daha sonraki bir zamanda, [IThreadProxy:: Sıchout](#switchout) yöntemini çağırarak Scheduler 'ın bıraktı olarak kabul edilir. `IThreadProxy::SwitchOut`Yöntemi, bir sanal işlemci kökü yeniden çizelgelemek için kullanılabilir olana kadar iş parçacığı proxy 'sini engelleyebilir.

`SwitchTo``IThreadProxy`Şu anda yürütülmekte olan iş parçacığını temsil eden arabirim üzerinde çağrılmalıdır veya sonuçlar tanımsız. `invalid_argument`Parametresi olarak ayarlandıysa, işlevi atar `pContext` `NULL` .

## <a name="ithreadproxyyieldtosystem-method"></a><a name="yieldtosystem"></a> IThreadProxy:: Ödemedtosystem yöntemi

Çağıran iş parçacığının, geçerli işlemcide çalıştırılmaya HAZIRAN başka bir iş parçacığına yürütülmesini sağlar. İşletim sistemi yürütülecek bir sonraki iş parçacığını seçer.

```cpp
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>Açıklamalar

Normal bir Windows iş parçacığı tarafından desteklenen bir iş parçacığı proxy 'si tarafından çağrıldığında, `YieldToSystem` tam olarak Windows işlevi gibi davranır `SwitchToThread` . Ancak, Kullanıcı modu zamanlanabilen (UMS) iş parçacıklarından çağrıldığında `SwitchToThread` işlevi, işletim sistemini değil, Kullanıcı modu zamanlayıcısına çalıştırılacak bir sonraki iş parçacığını seçme görevini devreder. Sistemde farklı bir ready iş parçacığına geçiş yapmanın istenen etkisini elde etmek için kullanın `YieldToSystem` .

`YieldToSystem``IThreadProxy`Şu anda yürütülmekte olan iş parçacığını temsil eden arabirim üzerinde çağrılmalıdır veya sonuçlar tanımsız.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IExecutionContext Yapısı](iexecutioncontext-structure.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)

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
ms.openlocfilehash: b87694393af4634ec97d05070aa5513cd132098a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854223"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy Yapısı

Yürütmenin iş parçacığı için bir soyutlama. Oluşturduğunuz Scheduler `SchedulerType` ilke anahtarına bağlı olarak, Kaynak Yöneticisi, size düzenli bir Win32 iş parçacığı veya Kullanıcı modu zamanlanabilen (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy 'si verir. UMS iş parçacıkları, Windows 7 ve üzeri sürümleri ile 64 bit işletim sistemlerinde desteklenir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IThreadProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IThreadProxy:: GetId](#getid)|İş parçacığı proxy 'si için benzersiz bir tanımlayıcı döndürür.|
|[IThreadProxy:: geçiş](#switchout)|Bağlamı temeldeki sanal işlemci kökünden ilişkilendirir.|
|[IThreadProxy:: SwitchTo](#switchto)|Şu anda yürütülmekte olan bağlamdan farklı bir içerik anahtarı gerçekleştirir.|
|[IThreadProxy:: Ödemedtosystem](#yieldtosystem)|Çağıran iş parçacığının, geçerli işlemcide çalıştırılmaya HAZIRAN başka bir iş parçacığına yürütülmesini sağlar. İşletim sistemi yürütülecek bir sonraki iş parçacığını seçer.|

## <a name="remarks"></a>Açıklamalar

İş parçacığı proxy 'leri, işi dağıtma yöntemi olarak `IExecutionContext` arabirim tarafından temsil edilen yürütme bağlamlarına bağlıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="getid"></a>IThreadProxy:: GetID Yöntemi

İş parçacığı proxy 'si için benzersiz bir tanımlayıcı döndürür.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Benzersiz bir tamsayı tanımlayıcısı.

## <a name="switchout"></a>IThreadProxy:: geçiş yöntemi

Bağlamı temeldeki sanal işlemci kökünden ilişkilendirir.

```cpp
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>Parametreler

*switchState*<br/>
Anahtarı yürüten iş parçacığı proxy 'sinin durumunu gösterir. Parametre `SwitchingProxyState`türündedir.

### <a name="remarks"></a>Açıklamalar

Herhangi bir nedenden dolayı bir bağlamın üzerinde yürütüldüğü sanal işlemci kökünden ilişkisini kaldırmak gerekirse `SwitchOut` kullanın. `switchState`parametresine geçirdiğiniz değere ve sanal bir işlemci kökünde yürütme yapılıp yapılmayacağını bağlı olarak, çağrı hemen döndürülür ya da bağlamla ilişkili iş parçacığı proxy 'sini engeller. Parametre `Idle`olarak ayarlanan `SwitchOut` çağırmak hatadır. Bunu yapmak [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel duruma neden olur.

`SwitchOut`, Scheduler 'ın sahip olduğu sanal işlemci köklerinin sayısını azaltmak istediğinizde yararlı olur, çünkü Kaynak Yöneticisi bunu sizin yapmanız, ancak geçici bir fazla abonelik sanal işlemci kökü isteğiniz ve bu işlemi gerçekleştirmek istiyormuş olmanız gerekir. Bu durumda, `Blocking`olarak ayarlanan parametre `switchState` bir `SwitchOut` çağrısı yapmadan önce sanal işlemci kökünde [IVirtualProcessorRoot:: Remove](iexecutionresource-structure.md#remove) yöntemini çağırmanız gerekir. Bu işlem, iş parçacığı proxy 'sini engeller ve Scheduler 'da farklı bir sanal işlemci kökü yürütmek için kullanılabilir olduğunda yürütmeyi sürdürür. Blok iş parçacığı proxy 'si, bu iş parçacığı proxy 'sinin yürütme bağlamına geçmek için `SwitchTo` işlevi çağırarak devam edebilir. Ayrıca, bir sanal işlemci kökünü etkinleştirmek için ilişkili bağlamını kullanarak iş parçacığı proxy 'sini de sürdürebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate).

`SwitchOut`, sanal işlemciyi yeniden başlatmak istediğinizde de kullanılabilir. böylece, iş parçacığı proxy 'sini engelliyor veya üzerinde çalıştığı sanal işlemci kökünden geçici olarak bir süre önce ve bunun için işi gönderen Zamanlayıcı, daha sonra etkinleştirilebilir. İş parçacığı proxy 'sini engellemek istiyorsanız, `SwitchOut` parametresi `switchState` `Blocking` olarak ayarlayın. Daha sonra yukarıda belirtilen `SwitchTo` veya `IVirtualProcessorRoot::Activate` kullanılarak devam edilebilir. Bu iş parçacığı proxy 'sini, üzerinde çalıştığı sanal işlemci kökünden ve Sanal işlemcinin ilişkilendirildiği Scheduler 'dan geçici olarak ayırmak istediğinizde, `Nesting` olarak ayarlanan `SwitchOut` kullanın. Bir sanal işlemci kökünde yürütüldüğü sırada `switchState` `Nesting` olarak ayarlanan parametre `SwitchOut` çağrılması, kökün yeniden başlatılmasına ve geçerli iş parçacığı proxy 'sine gerek olmadan yürütülmeye devam etmesine neden olur. İş parçacığı proxy 'si, daha sonraki bir zamanda `Blocking` ile [IThreadProxy:: geçiş](#switchout) yöntemini çağırarak Scheduler 'ı bıraktı olarak kabul edilir. `Blocking` olarak ayarlanan parametre `SwitchOut` ikinci çağrısı, bağlamı engellenen bir duruma döndürmeye yöneliktir, böylece `SwitchTo` ya da bu `IVirtualProcessorRoot::Activate` ayrılan zamanlayıcının üzerinden devam edebilir. Sanal işlemci kökünde yürütülmediği için yeniden başlatma gerçekleşmez.

Yeniden başlatılan bir sanal işlemci kökü, Scheduler 'ın Kaynak Yöneticisi tarafından verildiği yeni bir sanal işlemci kökünden farklı değildir. Bunu, `IVirtualProcessorRoot::Activate`kullanarak bir yürütme bağlamı ile etkinleştirerek yürütmek için kullanabilirsiniz.

`SwitchOut`, yürütülmekte olan iş parçacığını temsil eden `IThreadProxy` arabiriminde çağrılmalıdır ya da sonuçlar tanımsız.

Visual Studio 2010 ile birlikte gelen kitaplıklarda ve üstbilgilere bu yöntem bir parametre almadı ve sanal işlemci kökünü yeniden göndermedi. Eski davranışı korumak için `Blocking` varsayılan parametre değeri sağlanır.

## <a name="switchto"></a>IThreadProxy:: SwitchTo yöntemi

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
Anahtarı yürüten iş parçacığı proxy 'sinin durumunu gösterir. Parametre `SwitchingProxyState`türündedir.

### <a name="remarks"></a>Açıklamalar

İlk yürütme bağlamının [IExecutionContext::D ispatch](iexecutioncontext-structure.md#dispatch) yönteminden bir yürütme bağlamından diğerine geçiş yapmak için bu yöntemi kullanın. Yöntemi, zaten bir ilişkili değilse, yürütme bağlamını `pContext` bir iş parçacığı proxy 'si ile ilişkilendirir. Geçerli iş parçacığı proxy 'sinin sahipliği, `switchState` bağımsız değişkeni için belirttiğiniz değere göre belirlenir.

Şu anda yürütülmekte olan iş parçacığı proxy 'sini Kaynak Yöneticisi döndürmek istediğinizde `Idle` değerini kullanın. `SwitchTo` `switchState` `Idle` olarak ayarlanan parametre ile çağırmak, yürütme bağlamı `pContext` temel yürütme kaynağında yürütülmeye başlamasına neden olur. Bu iş parçacığı proxy 'sinin sahipliği Kaynak Yöneticisi aktarılır ve aktarım işleminin tamamlanabilmesi için `SwitchTo` döndürmeden sonra yürütme bağlamının `Dispatch` yönteminden geri dönmesinin beklendiğinden. İş parçacığı proxy 'sinin gönderildiği yürütme bağlamı, iş parçacığı proxy 'sinden ilişkisi kesildi ve Zamanlayıcı onu yeniden kullanmak veya uygun gördüğü sürece yok etmek için ücretsizdir.

Bu iş parçacığı proxy 'sinin engellenen bir durum girmesini istediğinizde `Blocking` değerini kullanın. `SwitchTo` `switchState` `Blocking` olarak ayarlanan parametre ile çağırmak, yürütme bağlamı `pContext` yürütülmeye başlamasına neden olur ve devam edene kadar geçerli iş parçacığı proxy 'sini engeller. Zamanlayıcı, iş parçacığı proxy `Blocking` durumundayken iş parçacığı proxy 'sinin sahipliğini korur. Blok iş parçacığı proxy 'si, bu iş parçacığı proxy 'sinin yürütme bağlamına geçmek için `SwitchTo` işlevi çağırarak devam edebilir. Ayrıca, bir sanal işlemci kökünü etkinleştirmek için ilişkili bağlamını kullanarak iş parçacığı proxy 'sini de sürdürebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate).

Bu iş parçacığı proxy 'sini, üzerinde çalıştığı sanal işlemci kökünden ve için iş Gönderen Scheduler 'dan geçici olarak ayırmak istediğinizde `Nesting` değerini kullanın. `SwitchTo` `switchState` `Nesting` olarak ayarlanan parametre ile çağırmak, yürütme bağlamı `pContext` yürütülmeye başlamasına neden olur ve geçerli iş parçacığı proxy 'si, sanal işlemci köküne gerek olmadan yürütmeye devam eder. İş parçacığı proxy 'si, daha sonraki bir zamanda, [IThreadProxy:: Sıchout](#switchout) yöntemini çağırarak Scheduler 'ın bıraktı olarak kabul edilir. `IThreadProxy::SwitchOut` yöntemi, bir sanal işlemci kökü yeniden çizelgelemek için kullanılabilir olana kadar iş parçacığı proxy 'sini engelleyebilir.

`SwitchTo`, yürütülmekte olan iş parçacığını temsil eden `IThreadProxy` arabiriminde çağrılmalıdır ya da sonuçlar tanımsız. `pContext` parametresi `NULL`olarak ayarlandıysa işlev `invalid_argument` atar.

## <a name="yieldtosystem"></a>IThreadProxy:: Ödemedtosystem yöntemi

Çağıran iş parçacığının, geçerli işlemcide çalıştırılmaya HAZIRAN başka bir iş parçacığına yürütülmesini sağlar. İşletim sistemi yürütülecek bir sonraki iş parçacığını seçer.

```cpp
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>Açıklamalar

Normal bir Windows iş parçacığı tarafından desteklenen bir iş parçacığı proxy 'si tarafından çağrıldığında, `YieldToSystem` tam olarak Windows işlevi `SwitchToThread`gibi davranır. Ancak, Kullanıcı modu zamanlanabilen (UMS) iş parçacıklarından çağrıldığında `SwitchToThread` işlevi, işletim sistemini değil Kullanıcı modu zamanlayıcısına çalıştırılacak bir sonraki iş parçacığını seçme görevini devreder. Sistemde farklı bir ready iş parçacığına geçiş yapmanın istenen etkisini elde etmek için `YieldToSystem`kullanın.

`YieldToSystem`, yürütülmekte olan iş parçacığını temsil eden `IThreadProxy` arabiriminde çağrılmalıdır ya da sonuçlar tanımsız.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IExecutionContext Yapısı](iexecutioncontext-structure.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)

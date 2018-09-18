---
title: Ithreadproxy yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
dev_langs:
- C++
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3be0a32de4e0e5b57471722ffa2cf8fcea5fd6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027862"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy Yapısı
Bir iş parçacığı için bir soyutlamayı yürütme. Yapılandırmanıza bağlı olarak `SchedulerType` oluşturduğunuz Zamanlayıcı ilke anahtarı, kaynak yöneticisi vermek, normal bir Win32 iş parçacığı veya bir kullanıcı modunda zamanlanabilen (UMS) iş parçacığı tarafından desteklenen bir iş parçacığı proxy'sini. UMS iş parçacıkları, sürümü Windows 7 64-bit işletim sistemlerinde desteklenen ve daha yüksek.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IThreadProxy;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ithreadproxy::GetID](#getid)|İş parçacığı proxy için benzersiz bir tanımlayıcı döndürür.|  
|[Ithreadproxy::switchout](#switchout)|Bağlam arka plandaki sanal işlemci kökünden ayırır.|  
|[Ithreadproxy::switchto](#switchto)|Bir ortak bağlam anahtarı şu anda yürütülen bağlamından farklı bir gerçekleştirir.|  
|[Ithreadproxy::yieldtosystem](#yieldtosystem)|Geçerli işlemci üzerinde çalıştırmak hazır olan başka bir iş parçacığına yürütme elde etmek üzere çağıran iş parçacığını neden olur. İşletim sistemi, yürütülecek sonraki iş parçacığını seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı proxy yürütme bağlamları arabirim tarafından temsil edilen için sıkı bağlı `IExecutionContext` iş gönderme olarak.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IThreadProxy`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getid"></a>  Ithreadproxy::GetID metodu  
 İş parçacığı proxy için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı benzersiz tanımlayıcısı.  
  
##  <a name="switchout"></a>  Ithreadproxy::switchout yöntemi  
 Bağlam arka plandaki sanal işlemci kökünden ayırır.  
  
```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*switchState*<br/>
Geçişi yürüten iş parçacığı proxy durumunu belirtir. Parametre türüdür `SwitchingProxyState`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `SwitchOut` bir bağlam üzerinde yürütülen, herhangi bir nedenle sanal işlemci kökünden ilişkisini gerekiyorsa. Değere göre parametresi için geçirdiğiniz `switchState`, ve bir sanal işlemci kökünde Yürütülüyor olsun veya olmasın, çağrı ya hemen döndürür veya bağlamla ilişkilendirilen iş parçacığı proxy'sini engellemek. Çağırmak için bir hata olduğunu `SwitchOut` ayarlanan parametre ile `Idle`. Bunun yapılması sonucunda bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum.  
  
 `SwitchOut` scheduler, kaynak yöneticisi yapmanızı söylediği veya geçici zamanlayıcınızın sanal işlemci kök istenen ve çalışmayı kökle sayısını azaltmak istediğinizde yararlıdır. Bu durumda yöntem çağırması gereken [IVirtualProcessorRoot::Remove](iexecutionresource-structure.md#remove) bir çağrı yapmadan önce sanal işlemci kökünde `SwitchOut` parametresiyle `switchState` kümesine `Blocking`. Bu iş parçacığı proxy'sini engeller ve bir zamanlayıcı farklı sanal işlemci kök, onu yürütmek kullanılabilir olduğunda yürütmeyi devam ettirir. Engelleyen iş parçacığı proxy'si işlevini çağırarak sürdürülebilir `SwitchTo` bu iş parçacığı proxy'sinin yürütme bağlamına geçmek için. Bir sanal işlemci kökünü etkinleştirmek üzere ilişkili bağlamını kullanarak, iş parçacığı proxy'sini devam edebilir. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate).  
  
 `SwitchOut` Sanal işlemci onu gelecekte iş parçacığı proxy'sini engellerken veya sanal işlemci kökünden geçici olarak kullanımdan çıkarılıyor çalıştığı ve Zamanlayıcı, iş için ayırırken etkinleştirilebilmesi için yeniden başlatmak istediğinizde de kullanılabilir. Kullanım `SwitchOut` parametresiyle `switchState` kümesine `Blocking` iş parçacığı proxy'sini engellemek istiyorsanız. Kullanarak daha sonra sürdürülebilir `SwitchTo` veya `IVirtualProcessorRoot::Activate` yukarıda da belirtildiği gibi. Kullanım `SwitchOut` ayarlanan parametre ile `Nesting` ne zaman bu iş parçacığı proxy'sini, üzerinde çalıştığı sanal işlemci kökünden geçici olarak ayırmak istediğiniz ve Zamanlayıcı Sanal işlemcinin ilişkilendirilmiş olduğu. Çağırma `SwitchOut` parametresiyle `switchState` kümesine `Nesting` bir sanal işlemci kökünde yürütülürken kök başlatılmasına ve bir gerek kalmadan yürütmeye devam geçerli iş parçacığı proxy'sini neden olur. İş parçacığı proxy'sini çağırdığı kadar Zamanlayıcıdan kabul [Ithreadproxy::switchout](#switchout) yöntemiyle `Blocking` , bir sonraki bir noktada. İçin yapılan ikinci çağrı `SwitchOut` ayarlanan parametre ile `Blocking` bunu tarafından devam ettirilebilir böylece bağlamı engelli duruma geri dönmek için hedeflenen `SwitchTo` veya `IVirtualProcessorRoot::Activate` ayrıldığı Zamanlayıcı içinde. Bir sanal işlemci kökünde Yürütülüyor değil çünkü yürütülmediği gerçekleşir.  
  
 Yeniden başlatılan sanal işlemci kök, Zamanlayıcı'yı kaynak yöneticisi tarafından verilmiş olan yeni bir sanal işlemci kökünden farklı değildir. Bir yürütme bağlamı kullanarak ile etkinleştirerek onu yürütme için kullanabilirsiniz `IVirtualProcessorRoot::Activate`.  
  
 `SwitchOut` çağrılmalıdır `IThreadProxy` yürütülmekte olan iş parçacığını veya sonuçlarını temsil eden arabirim tanımlanmamıştır.  
  
 Visual Studio 2010 ile birlikte gelen üst bilgileri ve kitaplıkları, bu yöntem, bir parametre almaz ve sanal işlemci kökü başlatmazdı. Varsayılan parametre değeri eski davranışı korumak için `Blocking` sağlanır.  
  
##  <a name="switchto"></a>  Ithreadproxy::switchto yöntemi  
 Bir ortak bağlam anahtarı şu anda yürütülen bağlamından farklı bir gerçekleştirir.  
  
```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
*pContext*<br/>
İşbirliği ile geçmek için yürütme bağlamı.  
  
*switchState*<br/>
Geçişi yürüten iş parçacığı proxy durumunu belirtir. Parametre türüdür `SwitchingProxyState`.  
  
### <a name="remarks"></a>Açıklamalar  
 Tek bir yürütme bağlamında diğerine geçmek için bu yöntemi kullanın [Iexecutioncontext::Dispatch](iexecutioncontext-structure.md#dispatch) yöntemi ilk yürütme bağlamı. Yürütme bağlamı yöntemi ilişkilendirir `pContext` zaten ile ilişkili değilse, bir iş parçacığı proxy ile. Geçerli iş parçacığı proxy'sini sahipliğini için belirttiğiniz değere göre belirlenir `switchState` bağımsız değişken.  
  
 Değeri kullanın `Idle` şu anda yürütülen iş parçacığı proxy'sini Resource Manager'a döndürmek istediğinizde. Çağırma `SwitchTo` parametresiyle `switchState` kümesine `Idle` yürütme bağlamı neden olacak `pContext` temel yürütme kaynak çalıştırmaya başlamak için. Bu iş parçacığı proxy'sini sahipliğini Resource Manager'a aktarılır ve yürütme bağlamdan 's döndürmek için beklenen `Dispatch` yöntemi hemen sonra `SwitchTo` aktarımı tamamlamak için döndürür. İş parçacığı proxy'sini gönderme yürütme bağlamı iş parçacığı Ara sunucuya noktanızla ilişkisi silinir ve yeniden kullanmak veya uygun gördüğü şekilde yok etmek Zamanlayıcı ücretsizdir.  
  
 Değeri kullanın `Blocking` engellenmiş durumda girmek için bu iş parçacığı proxy'sini istediğinizde. Çağırma `SwitchTo` parametresiyle `switchState` kümesine `Blocking` yürütme bağlamı neden olacak `pContext` yürütmeye başlamak ve sürdürülene kadar geçerli iş parçacığı proxy'sini engellemek için. İş parçacığı proxy'sini olduğunda Zamanlayıcı iş parçacığı proxy'sini sahipliğini korur `Blocking` durumu. Engelleyen iş parçacığı proxy'si işlevini çağırarak sürdürülebilir `SwitchTo` bu iş parçacığı proxy'sinin yürütme bağlamına geçmek için. Bir sanal işlemci kökünü etkinleştirmek üzere ilişkili bağlamını kullanarak, iş parçacığı proxy'sini devam edebilir. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate).  
  
 Değeri kullanın `Nesting` ne zaman bu iş parçacığı proxy'sini, üzerinde çalıştığı sanal işlemci kökünden geçici olarak ayırmak istediğiniz ve Zamanlayıcı iş için gönderiyor. Çağırma `SwitchTo` parametresiyle `switchState` kümesine `Nesting` yürütme bağlamı neden olacak `pContext` yürütme ve geçerli iş parçacığı proxy'sini ayrıca bir sanal işlemci kökünde gerek kalmadan yürütmeye devam eder. İş parçacığı proxy'sini çağırdığı kadar Zamanlayıcıdan kabul [Ithreadproxy::switchout](#switchout) yöntemi, bir sonraki bir noktada. `IThreadProxy::SwitchOut` Yöntemi bir sanal işlemci kök, yeniden zamanlamak kullanılabilir hale gelene kadar iş parçacığı proxy'sini engellemek.  
  
 `SwitchTo` çağrılmalıdır `IThreadProxy` yürütülmekte olan iş parçacığını veya sonuçlarını temsil eden arabirim tanımlanmamıştır. İşlevin `invalid_argument` , parametre `pContext` ayarlanır `NULL`.  
  
##  <a name="yieldtosystem"></a>  Ithreadproxy::yieldtosystem yöntemi  
 Geçerli işlemci üzerinde çalıştırmak hazır olan başka bir iş parçacığına yürütme elde etmek üzere çağıran iş parçacığını neden olur. İşletim sistemi, yürütülecek sonraki iş parçacığını seçer.  
  
```
virtual void YieldToSystem() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Normal Windows, iş parçacığı tarafından desteklenen bir iş parçacığı proxy'sini tarafından çağrıldığında `YieldToSystem` tam olarak Windows işlev gibi davranan `SwitchToThread`. Ancak, kullanıcı modunda zamanlanabilen (UMS) parçacıklarından çağrıldığında `SwitchToThread` işlevi kullanıcı modu Zamanlayıcı işletim sistemini çalıştırmak için bir sonraki iş parçacığını çekme görevini atar. Sistemde farklı bir hazır iş parçacığına geçiş, istenilen etkiyi elde etmek için kullanmak `YieldToSystem`.  
  
 `YieldToSystem` çağrılmalıdır `IThreadProxy` yürütülmekte olan iş parçacığını veya sonuçlarını temsil eden arabirim tanımlanmamıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Iexecutioncontext yapısı](iexecutioncontext-structure.md)   
 [Ischeduler yapısı](ischeduler-structure.md)   
 [IVirtualProcessorRoot Yapısı](ivirtualprocessorroot-structure.md)

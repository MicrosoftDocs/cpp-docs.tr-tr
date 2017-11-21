---
title: "Ithreadproxy yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
dev_langs: C++
helpviewer_keywords: IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f56e7858fc313ac35d5a3937e2d64472f28e355d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ithreadproxy-structure"></a>IThreadProxy Yapısı
Bir iş parçacığı için bir Özet yürütme. Bağlı olarak `SchedulerType` oluşturduğunuz Zamanlayıcı İlkesi anahtarı Resource Manager vermek, normal bir Win32 iş parçacığı veya kullanıcı modu zamanlanabilir (UMS) iş parçacığı tarafından yedeklenen bir iş parçacığı proxy. UMS iş parçacığı desteklenen 64-bit işletim sistemi sürümü Windows 7 ve üzeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IThreadProxy;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ithreadproxy::GetID](#getid)|İş parçacığı proxy için benzersiz bir tanımlayıcı döndürür.|  
|[Ithreadproxy::switchout](#switchout)|Temel alınan sanal işlemci kök bağlamından keser.|  
|[Ithreadproxy::switchto](#switchto)|İşbirlikçi bağlam anahtarı şu anda yürütülen bağlamdan farklı bir gerçekleştirir.|  
|[Ithreadproxy::yieldtosystem](#yieldtosystem)|Geçerli İşlemci çalıştırılmaya hazır başka bir iş parçacığı için yürütme elde etmek üzere çağıran iş parçacığı neden olur. İşletim sistemi, yürütülecek sonraki iş parçacığı seçer.|  
  
## <a name="remarks"></a>Açıklamalar  
 İş parçacığı proxy'leri eşleşmiş arabirimi tarafından temsil edilen yürütme bağlamı için `IExecutionContext` iş gönderme olarak.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IThreadProxy`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getid"></a>Ithreadproxy::GetID yöntemi  
 İş parçacığı proxy için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı benzersiz tanımlayıcısı.  
  
##  <a name="switchout"></a>Ithreadproxy::switchout yöntemi  
 Temel alınan sanal işlemci kök bağlamından keser.  
  
```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `switchState`  
 Anahtar yürütme iş parçacığı proxy durumunu gösterir. Parametre türünde `SwitchingProxyState`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `SwitchOut` onu Yürütülüyor, herhangi bir nedenden dolayı sanal işlemci kök bağlamından ilişkisini gerekiyorsa. Değerin bağlı olarak, parametre geçirdiğiniz `switchState`, ve bir sanal işlemcinin kökünde yürütüyor olmadığını çağrı hemen geri veya bağlamla ilişkili iş parçacığı proxy engelleyin. Çağırmak için bir hata olduğunu `SwitchOut` kümesine parametresiyle `Idle`. Bunun yapılması neden olur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum.  
  
 `SwitchOut`Resource Manager bunu yapmanızı istedi olduğundan veya bir talep geçici sanal işlemci kök istenir ve çalışmayı olduğundan, Zamanlayıcı sahip sanal işlemci kökleri sayısını azaltmak istediğinizde kullanışlıdır. Bu durumda yöntemi çağıracağı [IVirtualProcessorRoot::Remove](http://msdn.microsoft.com/en-us/ad699b4a-1972-4390-97ee-9c083ba7d9e4) yapılan bir çağrı yapmadan önce sanal işlemci kökündeki `SwitchOut` parametresiyle `switchState` kümesine `Blocking`. Bu iş parçacığı proxy engeller ve farklı sanal işlemci kök Zamanlayıcı içinde çalıştırmak üzere kullanılabilir olduğunda yürütme devam eder. Engelleme iş parçacığı proxy işlevini çağırarak ettirilebilir `SwitchTo` bu iş parçacığı proxy'nin yürütme bağlamı değiştirmek için. Ayrıca, iş parçacığı proxy sanal işlemci kök etkinleştirmek için ilişkili bağlamını kullanarak da devam edebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate).  
  
 `SwitchOut`iş parçacığı proxy engelleme ya da geçici olarak sanal işlemci kökünden ayırma üzerinde çalıştırıldığı ve Zamanlayıcı iş için gönderiyor gelecekte etkinleştirilebilir şekilde sanal işlemci yeniden başlatmak istediğinizde de kullanılabilir. Kullanım `SwitchOut` parametresiyle `switchState` kümesine `Blocking` iş parçacığı proxy engellemek istiyorsanız. Kullanarak daha sonra ettirilebilir `SwitchTo` veya `IVirtualProcessorRoot::Activate` yukarıda da belirtildiği gibi. Kullanım `SwitchOut` kümesine parametresiyle `Nesting` zaman bu iş parçacığı proxy üzerinde çalıştığından sanal işlemci kök geçici olarak ayırmak istiyor ve Zamanlayıcı sanal işlemci ile ilişkili. Çağırma `SwitchOut` parametresiyle `switchState` kümesine `Nesting` sanal işlemci kökünde yürütülürken kök yeniden başlatılmasına ve bir gerek kalmadan yürütme devam etmek için geçerli iş parçacığı proxy neden olur. İş parçacığı proxy çağırır kadar Zamanlayıcı bıraktıysanız kabul [Ithreadproxy::switchout](#switchout) yöntemiyle `Blocking` , bir sonraki bir noktada. İkinci çağrı `SwitchOut` kümesine parametresiyle `Blocking` , ya da devam ettirilebilir böylece bağlam engellenen bir duruma döndürmek için tasarlanmıştır `SwitchTo` veya `IVirtualProcessorRoot::Activate` ayrılmış gelen zamanlayıcı içinde. Bir sanal işlemcinin kökünde yürütülmekte olan değil çünkü hiçbir yeniden başlatma gerçekleşir.  
  
 Yeniden başlatılan sanal işlemci kök, Zamanlayıcı'yı kaynak yöneticisi tarafından verilen yepyeni bir sanal işlemcinin kök farklı değildir. Yürütme için bir bağlam kullanılarak yürütme ile etkinleştirerek kullanabilmeniz için `IVirtualProcessorRoot::Activate`.  
  
 `SwitchOut`üzerinde çağrılmalıdır `IThreadProxy` şu anda yürütülen iş parçacığı veya sonuçlarını temsil eden arabirim tanımlanmamış.  
  
 Bu yöntem, kitaplıkları ve Visual Studio 2010 ile birlikte gelen üstbilgileri, bir parametre geçmeyecek ve sanal işlemci kök yeniden değil. Eski davranışı, varsayılan parametre değeri korumak için `Blocking` sağlanır.  
  
##  <a name="switchto"></a>Ithreadproxy::switchto yöntemi  
 İşbirlikçi bağlam anahtarı şu anda yürütülen bağlamdan farklı bir gerçekleştirir.  
  
```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 İşbirliği ile geçmek için yürütme bağlamı.  
  
 `switchState`  
 Anahtar yürütme iş parçacığı proxy durumunu gösterir. Parametre türünde `SwitchingProxyState`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir yürütme bağlamı diğerine geçmek için bu yöntemi kullanmak [Iexecutioncontext::Dispatch](iexecutioncontext-structure.md#dispatch) ilk yürütme bağlamı yöntemi. Yürütme bağlamı yöntemi ilişkilendirir `pContext` zaten biriyle ilişkili değilse, bir iş parçacığı proxy ile. Geçerli iş parçacığı proxy sahipliğini için belirttiğiniz değere göre belirlenir `switchState` bağımsız değişkeni.  
  
 Değeri kullanmak `Idle` Resource Manager şu anda yürütülen iş parçacığı proxy döndürmek istediğinizde. Çağırma `SwitchTo` parametresiyle `switchState` kümesine `Idle` yürütme bağlamı neden olacak `pContext` temel yürütme kaynakta çalıştırmaya başlamak için. Bu iş parçacığı proxy sahipliğini Resource Manager aktarılır ve yürütme bağlamı 's döndürmesi bekleniyor `Dispatch` yöntemi hemen sonra `SwitchTo` aktarımı tamamlamak için döndürür. İş parçacığı proxy göndermeyi yürütme bağlamı iş parçacığı proxy sunucudan ilişkilendirmesi ve onu tekrar veya görür uygun şekilde destroy Zamanlayıcı ücretsizdir.  
  
 Değeri kullanmak `Blocking` engelleme durumu girmek için bu iş parçacığı proxy istediğinizde. Çağırma `SwitchTo` parametresiyle `switchState` kümesine `Blocking` yürütme bağlamı neden olacak `pContext` çalıştırmaya başlamak ve sürdürülene kadar geçerli iş parçacığı proxy engellemek için. İş parçacığı proxy olduğunda Zamanlayıcı iş parçacığı proxy sahipliğini korur `Blocking` durumu. Engelleme iş parçacığı proxy işlevini çağırarak ettirilebilir `SwitchTo` bu iş parçacığı proxy'nin yürütme bağlamı değiştirmek için. Ayrıca, iş parçacığı proxy sanal işlemci kök etkinleştirmek için ilişkili bağlamını kullanarak da devam edebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [Ivirtualprocessorroot::Activate](ivirtualprocessorroot-structure.md#activate).  
  
 Değeri kullanmak `Nesting` zaman bu iş parçacığı proxy üzerinde çalıştığından sanal işlemci kök geçici olarak ayırmak istiyor ve Zamanlayıcı iş için gönderiyor. Çağırma `SwitchTo` parametresiyle `switchState` kümesine `Nesting` yürütme bağlamı neden olacak `pContext` yürütme ve geçerli başlatmak için iş parçacığı proxy ayrıca sanal işlemci kök gerek kalmadan yürütmeye devam eder. İş parçacığı proxy çağırır kadar Zamanlayıcı bıraktıysanız kabul [Ithreadproxy::switchout](#switchout) yöntemi, bir sonraki bir noktada. `IThreadProxy::SwitchOut` Yöntemi sanal işlemci kök onu yeniden zamanlamak kullanılabilir hale gelene kadar iş parçacığı proxy engelleme.  
  
 `SwitchTo`üzerinde çağrılmalıdır `IThreadProxy` şu anda yürütülen iş parçacığı veya sonuçlarını temsil eden arabirim tanımlanmamış. İşlev oluşturur `invalid_argument` varsa parametresi `pContext` ayarlanır `NULL`.  
  
##  <a name="yieldtosystem"></a>Ithreadproxy::yieldtosystem yöntemi  
 Geçerli İşlemci çalıştırılmaya hazır başka bir iş parçacığı için yürütme elde etmek üzere çağıran iş parçacığı neden olur. İşletim sistemi, yürütülecek sonraki iş parçacığı seçer.  
  
```
virtual void YieldToSystem() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Normal Windows, iş parçacığı tarafından yedeklenen bir iş parçacığı proxy tarafından çağrıldığında `YieldToSystem` tam olarak Windows işlevi gibi davranır `SwitchToThread`. Ancak, kullanıcı modu zamanlanabilir (UMS) parçacıklarından çağrıldığında `SwitchToThread` işlevi, kullanıcı modu Zamanlayıcı işletim sistemini çalıştırmak için sonraki iş parçacığı çekme görevini atar. Sistemde farklı bir hazır iş parçacığına değiştirme istenen etkisini elde etmek için kullanmak `YieldToSystem`.  
  
 `YieldToSystem`üzerinde çağrılmalıdır `IThreadProxy` şu anda yürütülen iş parçacığı veya sonuçlarını temsil eden arabirim tanımlanmamış.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Iexecutioncontext yapısı](iexecutioncontext-structure.md)   
 [Ischeduler yapısı](ischeduler-structure.md)   
 [Ivirtualprocessorroot yapısı](ivirtualprocessorroot-structure.md)

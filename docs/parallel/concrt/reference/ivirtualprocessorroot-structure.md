---
title: "Ivirtualprocessorroot yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
dev_langs: C++
helpviewer_keywords: IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8f7a7dbff547a0a2f3fba04c10ad9107af2a26ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot Yapısı
Bir iş parçacığı proxy yürütmek bir donanım iş parçacığı için bir Özet.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IVirtualProcessorRoot : public IExecutionResource;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Ivirtualprocessorroot::Activate](#activate)|Yürütme bağlamı arabirimiyle ilişkilendirilmiş iş parçacığı proxy neden `pContext` bu sanal işlemci kökünde çalıştırmaya başlamak için.|  
|[Ivirtualprocessorroot::Deactivate](#deactivate)|Yürütme bağlamı göndermeyi durdurmak için bu sanal işlemci kökünde şu anda yürütülmekte olan iş parçacığı proxy neden olur. İş parçacığı proxy yapılan çağrı sırasında yürütme devam edecek `Activate` yöntemi.|  
|[Ivirtualprocessorroot::ensurealltasksvisible](#ensurealltasksvisible)|Sistemdeki tüm işlemciler için görünür olmasını işlemcilerin tek tek bellek hiyerarşisi içinde depolanan verileri neden olur. Bu yöntem döndürmeden önce tam bellek sınırı tüm işlemcilerin yürütüldüğü sağlar.|  
|[Ivirtualprocessorroot::GetID](#getid)|Sanal işlemci kök için benzersiz bir tanımlayıcı döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Her sanal işlemci kök ilişkili yürütme kaynak vardır. `IVirtualProcessorRoot` Arabirimi devraldığı [Iexecutionresource](iexecutionresource-structure.md) arabirimi. Birden fazla sanal işlemci kökleri aynı temel alınan donanım iş parçacığına karşılık gelebilir.  
  
 Kaynak Yöneticisi Sanal işlemci kökleri için zamanlayıcılar kaynaklarına yönelik isteklere yanıt verir. Bir zamanlayıcı iş yürütme bağlamı ile etkinleştirerek gerçekleştirmek için bir sanal işlemcinin kök kullanabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Iexecutionresource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="activate"></a>Ivirtualprocessorroot::Activate yöntemi  
 Yürütme bağlamı arabirimiyle ilişkilendirilmiş iş parçacığı proxy neden `pContext` bu sanal işlemci kökünde çalıştırmaya başlamak için.  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 Bu sanal işlemci kökünde gönderilen yürütme bağlamı için bir arabirim.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir yürütme bağlamı arabirimle ilişkili değilse Kaynak Yöneticisi'ni bir iş parçacığı proxy sağlayın`pContext`  
  
 `Activate` Yöntemi yeni bir sanal işlemcinin kök kaynak yöneticisi tarafından döndürülen iş çalıştırmaya başlamak için ya da devre dışı bıraktı veya devre dışı bırakmak için bir sanal işlemcinin kök iş parçacığı proxy devam etmek için kullanılabilir. Bkz: [Ivirtualprocessorroot::Deactivate](#deactivate) devre dışı bırakma hakkında daha fazla bilgi için. Ne zaman, sürdürme parametresi devre dışı bırakılan sanal işlemci kök `pContext` sanal işlemci kök devre dışı bırakmak için kullanılan parametre ile aynı olması gerekir.  
  
 Bir sanal işlemcinin kök çağrıları sonraki çiftlerini ilk kez etkinleştirildikten sonra `Deactivate` ve `Activate` birbiriyle durumunu. Bu kaynak için bir çağrı almaya Yöneticisi için kabul edilebilir olduğu anlamına gelir `Activate` aldığı önce `Deactivate` amacı için çağrısı.  
  
 Bir sanal işlemcinin kök etkinleştirdiğinizde, bu sanal işlemci kök ile iş şu anda meşgul Resource Manager sinyal. Bu kök yürütmek için herhangi bir iş, Zamanlayıcı bulamazsanız, çağrılacak beklenir `Deactivate` Kaynak Yöneticisi Sanal işlemci kök boşta olduğunu bildiren yöntemi. Kaynak Yöneticisi, sistem dengelemek üzere bu verileri kullanır.  
  
 `invalid_argument`varsa durum bağımsız değişkeni `pContext` değerine sahip `NULL`.  
  
 `invalid_operation`varsa durum bağımsız değişkeni `pContext` bu sanal işlemci kök tarafından en son gönderildi yürütme bağlamı temsil etmiyor.  
  
 Bir sanal işlemcinin kök etkinleştirme işlemi tarafından temel alınan donanım iş parçacığı abonelik düzeyini artırır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="deactivate"></a>Ivirtualprocessorroot::Deactivate yöntemi  
 Yürütme bağlamı göndermeyi durdurmak için bu sanal işlemci kökünde şu anda yürütülmekte olan iş parçacığı proxy neden olur. İş parçacığı proxy yapılan çağrı sırasında yürütme devam edecek `Activate` yöntemi.  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 Bu kök tarafından şu anda dağıtıldığı bağlamı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Boole değeri. Değerini `true` iş parçacığı proxy sunucudan döndürülen gösterir `Deactivate` yanıt olarak yapılan bir çağrı yöntemi `Activate` yöntemi. Değerini `false` iş parçacığı proxy Kaynak Yöneticisi'nde bir bildirim olaya yanıt olarak yönteminden döndürülen gösterir. Bir kullanıcı modu zamanlanabilir (UMS) iş parçacığı Zamanlayıcı üzerinde bu öğeleri scheduler'ın tamamlama listede görünen ve Zamanlayıcı bunları işlemek için gerekli gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir iş Zamanlayıcısı'nda bulamadığında sanal işlemci kök yürütme geçici olarak durdurmak için bu yöntemi kullanın. Çağrı `Deactivate` yöntemi gerekir kaynaklanan içinden `Dispatch` sanal işlemci kök ile en son etkinleştirilmesinden yöntemi yürütme bağlamı. Diğer bir deyişle, çağırma iş parçacığı proxy `Deactivate` yöntemi sanal işlemci kök yürütülmekte biri olması gerekir. Yöntemi, üzerinde yürütülen olmayan bir sanal işlemcinin kök çağırma tanımsız davranışlara neden.  
  
 Devre dışı bırakılan sanal işlemci kök çağrısıyla uyandırılabilir `Activate` yöntemi için geçirildi aynı bağımsız değişkeni ile `Deactivate` yöntemi. Zamanlayıcı, çağrılar sağlayan `Activate` ve `Deactivate` yöntemleri eşleştirilmiş, ancak bunlar belirli bir sırada alınabilmesi için gerekli değildir. Kaynak Yöneticisi için bir çağrı alma işleyebilir `Activate` yapılan bir çağrı almadan önce yöntem `Deactivate` amacı için yöntem.  
  
 Sanal işlemci kök awakens varsa ve dönüş değerini `Deactivate` yöntemi değerdir `false`, zamanlayıcı aracılığıyla UMS tamamlanma listesi sorgu `IUMSCompletionList::GetUnblockNotifications` yöntemi, işlem bu bilgilere dayanarak ve sonradan çağrısı`Deactivate`yeniden yöntemi. Bu tür sürede kadar tekrarlanmalıdır `Deactivate` yöntemi değeri döndürür `true`.  
  
 `invalid_argument`varsa durum bağımsız değişkeni `pContext` değerine sahip `NULL`.  
  
 `invalid_operation`Sanal işlemci kök hiç etkinleştirilmemişse, durum ya da bağımsız değişkeni `pContext` bu sanal işlemci kök tarafından en son gönderildi yürütme bağlamı temsil etmiyor.  
  
 Bir sanal işlemcinin kök devre dışı bırakma işlemi temel alınan donanım iş parçacığı abonelik düzeyi birer birer azaltır. Abonelik düzeyleri hakkında daha fazla bilgi için bkz: [Iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="ensurealltasksvisible"></a>Ivirtualprocessorroot::ensurealltasksvisible yöntemi  
 Sistemdeki tüm işlemciler için görünür olmasını işlemcilerin tek tek bellek hiyerarşisi içinde depolanan verileri neden olur. Bu yöntem döndürmeden önce tam bellek sınırı tüm işlemcilerin yürütüldüğü sağlar.  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pContext`  
 Bu sanal işlemci kök tarafından şu anda dağıtıldığı bağlamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Devre dışı bırakma sanal işlemci kök yeni iş Zamanlayıcı içine eklenmesi ile eşitlemek için istediğiniz zaman bu yöntem yararlı bulabilirsiniz. Performans nedenleriyle bir işlemci, yürütme iş parçacığı tarafından eklenen iş öğeleri için diğer tüm işlemcilerin hemen görünmez anlamına gelir bir bellek engelle çalıştırmadan, Zamanlayıcı iş öğelerini eklemek karar verebilirsiniz. İle birlikte bu yöntemi kullanarak `Deactivate` emin olun, Zamanlayıcı tüm sanal işlemci deactivate değil yöntemi kökleri iş öğeleri, scheduler'ın koleksiyonlarda varken.  
  
 Çağrı `EnsureAllTasksVisibleThe` yöntemi gerekir kaynaklanan içinden `Dispatch` sanal işlemci kök ile en son etkinleştirilmesinden yöntemi yürütme bağlamı. Diğer bir deyişle, çağırma iş parçacığı proxy `EnsureAllTasksVisible` yöntemi sanal işlemci kök yürütülmekte biri olması gerekir. Yöntemi, üzerinde yürütülen olmayan bir sanal işlemcinin kök çağırma tanımsız davranışlara neden.  
  
 `invalid_argument`varsa durum bağımsız değişkeni `pContext` değerine sahip `NULL`.  
  
 `invalid_operation`Sanal işlemci kök hiç etkinleştirilmemişse, durum ya da bağımsız değişkeni `pContext` bu sanal işlemci kök tarafından en son gönderildi yürütme bağlamı temsil etmiyor.  
  
##  <a name="getid"></a>Ivirtualprocessorroot::GetID yöntemi  
 Sanal işlemci kök için benzersiz bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayı tanımlayıcısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)

---
title: "Bağlam sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Context
- CONCRT/concurrency::Context
- CONCRT/concurrency::Context::Block
- CONCRT/concurrency::Context::CurrentContext
- CONCRT/concurrency::Context::GetId
- CONCRT/concurrency::Context::GetScheduleGroupId
- CONCRT/concurrency::Context::GetVirtualProcessorId
- CONCRT/concurrency::Context::Id
- CONCRT/concurrency::Context::IsCurrentTaskCollectionCanceling
- CONCRT/concurrency::Context::IsSynchronouslyBlocked
- CONCRT/concurrency::Context::Oversubscribe
- CONCRT/concurrency::Context::ScheduleGroupId
- CONCRT/concurrency::Context::Unblock
- CONCRT/concurrency::Context::VirtualProcessorId
- CONCRT/concurrency::Context::Yield
dev_langs: C++
helpviewer_keywords: Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dc49f795fb4c8f987271bd4f147a04e3ac873e33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="context-class"></a>Bağlam Sınıfı
Yürütme bağlamı için bir Özet temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class Context;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[~ Context yok Edicisi](#dtor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Engelle](#block)|Geçerli bağlam engeller.|  
|[CurrentContext](#currentcontext)|Bir işaretçi geçerli bağlamda döndürür.|  
|[GetID](#getid)|Bağlam ait olduğu Zamanlayıcı içinde benzersizdir bağlamı için bir tanımlayıcı döndürür.|  
|[Getschedulegroupıd](#getschedulegroupid)|Bağlam üzerinde çalışmakta zamanlama grubu için bir tanımlayıcı döndürür.|  
|[Getvirtualprocessorıd](#getvirtualprocessorid)|Bağlam üzerinde yürütme sanal işlemci için bir tanımlayıcı döndürür.|  
|[Kimliği](#id)|Geçerli bağlam ait olduğu Zamanlayıcı içinde benzersiz olduğundan geçerli bağlam için bir tanımlayıcı döndürür.|  
|[Iscurrenttaskcollectioncanceling](#iscurrenttaskcollectioncanceling)|Olup olmadığının göstergesi bir döndürür, satır içi geçerli bağlama göre şu anda yürütülmekte görev koleksiyonu etkin bir iptal ortasında (veya kısa bir süre içinde olacaktır).|  
|[Issynchronouslyblocked](#issynchronouslyblocked)|Bağlam zaman uyumlu olarak engellenmiş olup olmadığını belirler. Bir bağlam açıkça engellemek üzere sonuçlanan bir eylem gerçekleştirirse zaman uyumlu olarak engellenmesi olarak kabul edilir.|  
|[Oversubscribe](#oversubscribe)|Bir ek sanal işlemci bu Zamanlayıcı sanal işlemciler birinde yürütme bağlamı üzerinde çağrıldığında kod bloğu boyunca bir zamanlayıcı yerleştirir.|  
|[Schedulegroupıd](#schedulegroupid)|Geçerli bağlam üzerinde çalıştığı zamanlama grubu için bir tanımlayıcı döndürür.|  
|[Engellemeyi Kaldır](#unblock)|Bağlam engelini kaldırır ve runnable duruma neden olur.|  
|[Virtualprocessorıd](#virtualprocessorid)|Geçerli bağlam yürütülmekte olduğu sanal işlemci için bir tanımlayıcı döndürür.|  
|[Uyarı simgesi](#yield)|Başka bir bağlam çalıştırabilmeniz için yürütmeyi verir. Diğer bir bağlam için elde etmek üzere kullanılabilir durumdaysa, Zamanlayıcı başka bir işletim sistemi iş parçacığına yol açabilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık Çalışma zamanı Zamanlayıcısı'nı (bkz [Zamanlayıcı](scheduler-class.md)) çalışmayı yürütmek için kullandığı yürütme bağlamı için uygulamanız tarafından sıraya. Win32 iş parçacığı, bir Windows işletim sisteminde bir yürütme bağlamı örneğidir.  
  
 Herhangi bir zamanda bir zamanlayıcı eşzamanlılık düzeyi için kaynak yöneticisi tarafından verilen sanal işlemcilerin sayısı eşittir. Bir sanal işlemcinin bir işlem kaynağı ve temeldeki sistemi donanım parçacığında eşlenir bir soyutlamadır. Yalnızca tek Zamanlayıcı bağlamında bir sanal işlemcinin üzerinde belirli bir zamanda çalıştırabilirsiniz.  
  
 Zamanlayıcı doğası gereği işbirlikçi ve bekleme durumuna girerek isterse, bir yürütme bağlamı sanal işlemcisinin farklı bir bağlam için herhangi bir zamanda yol açabilir. Bekleme, yerine getirdiğinizde, yürütülmekte kullanılabilir bir sanal işlemcinin Zamanlayıcı'dan başlar kadar devam edilemiyor.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Context`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="block"></a>Engelle 

 Geçerli bağlam engeller.  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
 Çağıran bağlamını bir sanal işlemcinin üzerinde çalışıyorsa, sanal işlemci execute veya potansiyel olarak yapabilirsiniz başka runnable içeriği bulacaksınız yeni bir tane oluşturun.  
  
 Sonra `Block` yöntemi çağrıldı veya çağrılacağı, siz onu çağrısıyla eşleştirin gerekir [Engellemeyi Kaldır](#unblock) sırayla yeniden çalıştırmak için başka bir yürütme bağlamı yönteminden. Olduğunu bir kritik süre kodunuzu arayabilmesi için başka bir iş parçacığının kendi bağlamının yayımladığı noktası arasında unutmayın `Unblock` yöntemi ve burada gerçek yöntemi çağırmak için noktası `Block` yapılır. Bu süre boyunca, hangi sırayla engelleyebilir ve kendi nedeniyle (örneğin, bir kilit alınırken) engellemesini herhangi bir yöntemi çağırmanız gerekir değil. Çağrılar `Block` ve `Unblock` yöntemi engelleme ve engellemelerini kaldırma nedeni izleme. Yalnızca bir nesne sahipliğini olmalıdır bir `Block` -  `Unblock` çifti.  
  
 Bu yöntemi özel durumlar dahil olmak üzere, çeşitli atabilirsiniz [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md).  
  
##  <a name="dtor"></a>~ Bağlamı 

```
virtual ~Context();
```  
  
##  <a name="currentcontext"></a>CurrentContext 

 Bir işaretçi geçerli bağlamda döndürür.  
  
```
static Context* __cdecl CurrentContext();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
##  <a name="getid"></a>GetID 

 Bağlam ait olduğu Zamanlayıcı içinde benzersizdir bağlamı için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlam ait olduğu Zamanlayıcı içinde benzersizdir bağlamı için bir tanımlayıcı.  
  
##  <a name="getschedulegroupid"></a>Getschedulegroupıd 

 Bağlam üzerinde çalışmakta zamanlama grubu için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetScheduleGroupId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zamanlama grubu bağlamı için bir tanımlayıcı üzerinde şu anda çalışıyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemden dönüş değeri bağlam üzerinde yürütüyor zamanlama grubunun bir anlık örnekleme değeridir. Bu yöntem, geçerli bağlamı farklı bir bağlam çağrılırsa, değer döndürülür ve bağlı dayanıyordu olamaz şu anda eski olabilir. Genellikle, bu yöntem, hata ayıklama veya yalnızca izleme için kullanılır.  
  
##  <a name="getvirtualprocessorid"></a>Getvirtualprocessorıd 

 Bağlam üzerinde yürütme sanal işlemci için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlam şu anda bir sanal işlemcinin bağlam üzerinde yürütme sanal işlemci için bir tanımlayıcı yürütülen Aksi takdirde, değer `-1`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemden dönüş değeri bağlam yürütülmekte olduğu sanal işlemcinin bir anlık örnekleme değeridir. Bu değer döndürülür ve bağlı dayanıyordu olamaz şu anda eski olabilir. Genellikle, bu yöntem, hata ayıklama veya yalnızca izleme için kullanılır.  
  
##  <a name="id"></a>Kimliği 

 Geçerli bağlam ait olduğu Zamanlayıcı içinde benzersiz olduğundan geçerli bağlam için bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir zamanlayıcı bağlıysa, geçerli bağlam için geçerli bağlam ait olduğu Zamanlayıcı içinde benzersiz tanımlayıcıdır; Aksi takdirde, değer `-1`.  
  
##  <a name="iscurrenttaskcollectioncanceling"></a>Iscurrenttaskcollectioncanceling 

 Olup olmadığının göstergesi bir döndürür, satır içi geçerli bağlama göre şu anda yürütülmekte görev koleksiyonu etkin bir iptal ortasında (veya kısa bir süre içinde olacaktır).  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir zamanlayıcı arama bağlamına bağlı olduğu ve bir görev grubu bu bağlamda bir görev satır içi yürütüyor, göstergesidir olup, görev grubu ortasında etkin bir iptal (veya kısa bir süre içinde olacaktır); Aksi takdirde, değer `false`.  
  
##  <a name="issynchronouslyblocked"></a>Issynchronouslyblocked 

 Bağlam zaman uyumlu olarak engellenmiş olup olmadığını belirler. Bir bağlam açıkça engellemek üzere sonuçlanan bir eylem gerçekleştirirse zaman uyumlu olarak engellenmesi olarak kabul edilir.  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup bağlam zaman uyumlu olarak engellendi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bağlam açıkça engellemek üzere sonuçlanan bir eylem gerçekleştirirse zaman uyumlu olarak engellenmesi olarak kabul edilir. İş parçacığı zamanlayıcıda bu doğrudan arama gösterir `Context::Block` yöntemi veya kullanılarak oluşturulan bir eşitleme nesnesi `Context::Block` yöntemi.  
  
 Bu yöntemden dönüş değeri bağlam zaman uyumlu olarak engellenmiş olan anlık bir örnektir. Bu değer döndürülür ve yalnızca belirli koşullar altında kullanılabilir şu anda eski olabilir.  
  
##  <a name="operator_delete"></a>delete işleci 

 A `Context` nesne çalışma zamanı tarafından dahili olarak yok. Açıkça silinemiyor.  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PObject`  
 Silinecek nesne için bir işaretçi.  
  
##  <a name="oversubscribe"></a>Oversubscribe 

 Bir ek sanal işlemci bu Zamanlayıcı sanal işlemciler birinde yürütme bağlamı üzerinde çağrıldığında kod bloğu boyunca bir zamanlayıcı yerleştirir.  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>Parametreler  
 `_BeginOversubscription`  
 Varsa `true`, bir ek sanal işlemci aşırı abonelik süresince eklenmelidir göstergesidir. Varsa `false`, aşırı abonelik sona ereceği ve önceden eklenmiş sanal işlemci kaldırılmalı göstergesidir.  
  
##  <a name="schedulegroupid"></a>Schedulegroupıd 

 Geçerli bağlam üzerinde çalıştığı zamanlama grubu için bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir zamanlayıcı bağlı olduğu ve bir zamanlama grup üzerinde çalışan, Zamanlayıcı için bir tanımlayıcı grubuna geçerli bağlamı üzerinde çalıştığı; Aksi takdirde, değer `-1`.  
  
##  <a name="unblock"></a>Engellemeyi Kaldır 

 Bağlam engelini kaldırır ve runnable duruma neden olur.  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı için mükemmel yasal `Unblock` karşılık gelen çağrıyı önce gelen yöntemi [blok](#block) yöntemi. Çağrı sürece `Block` ve `Unblock` yöntemleri düzgün eşlenmemiş, çalışma zamanı ya da sipariş doğal yarış düzgün bir şekilde işler. Bir `Unblock` çağrısı önce gelen bir `Block` çağrısı yalnızca etkisini `Block` çağırın.  
  
 Bu yöntemle atılabilen çeşitli özel durumlar vardır. Bir bağlam çağrısı girişiminde bulunursa `Unblock` kendisi, yöntemi bir [context_self_unblock](context-self-unblock-class.md) özel durum. Varsa çağrılar `Block` ve `Unblock` düzgün eşleştirilmelidir değil (örneğin, iki çağrılar `Unblock` şu anda çalışan bir bağlam için yapılan), bir [context_unblock_unbalanced](context-unblock-unbalanced-class.md) özel durum.  
  
 Olduğunu bir kritik süre kodunuzu arayabilmesi için başka bir iş parçacığının kendi bağlamının yayımladığı noktası arasında unutmayın `Unblock` yöntemi ve burada gerçek yöntemi çağırmak için noktası `Block` yapılır. Bu süre boyunca, hangi sırayla engelleyebilir ve kendi nedeniyle (örneğin, bir kilit alınırken) engellemesini herhangi bir yöntemi çağırmanız gerekir değil. Çağrılar `Block` ve `Unblock` yöntemi engelleme ve engellemelerini kaldırma nedeni izleme. Yalnızca bir nesne sahipliğini olmalıdır bir `Block` ve `Unblock` çifti.  
  
##  <a name="virtualprocessorid"></a>Virtualprocessorıd 

 Geçerli bağlam yürütülmekte olduğu sanal işlemci için bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için geçerli bağlam yürütülmekte olduğu sanal işlemcinin bir tanımlayıcı bir zamanlayıcı bağlıysa; Aksi takdirde, değer `-1`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemden dönüş değeri geçerli bağlamı yürütülmekte olduğu sanal işlemcinin bir anlık örnekleme değeridir. Bu değer döndürülür ve bağlı dayanıyordu olamaz şu anda eski olabilir. Genellikle, bu yöntem, hata ayıklama veya yalnızca izleme için kullanılır.  
  
##  <a name="yield"></a>Uyarı simgesi 

 Başka bir bağlam çalıştırabilmeniz için yürütmeyi verir. Diğer bir bağlam için elde etmek üzere kullanılabilir durumdaysa, Zamanlayıcı başka bir işletim sistemi iş parçacığına yol açabilir.  
  
```
static void __cdecl Yield();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
##  <a name="yieldexecution"></a>YieldExecution 

 Başka bir bağlam çalıştırabilmeniz için yürütmeyi verir. Diğer bir bağlam için elde etmek üzere kullanılabilir durumdaysa, Zamanlayıcı başka bir işletim sistemi iş parçacığına yol açabilir.  
  
```
static void __cdecl YieldExecution();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda arama bağlamla ilişkili hiçbir Zamanlayıcı ise arama bağlamına bağlı işlem varsayılan Zamanlayıcı neden olur.  
  
 Bu yeni bir işlevidir [!INCLUDE[vs_dev14](../../../ide/includes/vs_dev14_md.md)] ve aynıdır [verim](#yield) çalışır ancak Windows.h verim makro çakışmayan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)   
 [Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




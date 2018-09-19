---
title: Bağlam sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4a62f6e569e123b9612e922e2d7c70787371afc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136185"
---
# <a name="context-class"></a>Bağlam Sınıfı
Bir yürütme bağlamı için bir soyutlamayı temsil eder.  
  
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
|[Block](#block)|Geçerli bağlamı engeller.|  
|[CurrentContext](#currentcontext)|Geçerli bağlama bir işaretçi döndürür.|  
|[GetId](#getid)|Bağlamın ait olduğu zamanlayıcıda benzersiz olan bağlam için bir tanımlayıcı döndürür.|  
|[GetScheduleGroupId](#getschedulegroupid)|Bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı döndürür.|  
|[GetVirtualProcessorId](#getvirtualprocessorid)|Bağlamın üzerinde yürütülmekte olduğu sanal işlemci için bir tanımlayıcı döndürür.|  
|[Kimliği](#id)|Geçerli bağlamın ait olduğu zamanlayıcıda benzersiz olan geçerli bağlam için bir tanımlayıcı döndürür.|  
|[Iscurrenttaskcollectioncanceling](#iscurrenttaskcollectioncanceling)|Döndürür bir işaret olup geçerli bağlamda satır içi şu anda yürütülmekte olan görev koleksiyonunun etkin bir iptalin ortasında (veya kısa süre içinde olacaktır).|  
|[Issynchronouslyblocked](#issynchronouslyblocked)|Bağlamın eş zamanlı olarak engellenip olup olmadığını belirler. Bir bağlam açıkça engellemeyle eylem gerçekleştirilen, zaman uyumlu olarak engellendiği kabul edilir.|  
|[Oversubscribe](#oversubscribe)|Bağlam, Zamanlayıcı içindeki sanal işlemcilerin birinde yürütülürken çağrıldığında kod bloğunun süresi için bir zamanlayıcıya ek bir sanal işlemci ekler.|  
|[ScheduleGroupId](#schedulegroupid)|Geçerli bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı döndürür.|  
|[Engellemeyi Kaldır](#unblock)|Engellemesini kaldırır ve çalıştırılabilir duruma gelmesine neden olur.|  
|[VirtualProcessorId](#virtualprocessorid)|Geçerli bağlamın üzerinde yürütülmekte olduğu sanal işlemci için bir tanımlayıcı döndürür.|  
|[yield](#yield)|Başka bir bağlamın çalıştırılabilmesi için yürütmeyi verir. Zamanlayıcı, başka bir bağlam için yield kullanılabilir haldeyse, başka bir işletim sistemi iş parçacığı verebilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Eşzamanlılık Çalışma zamanı Zamanlayıcısı (bkz [Zamanlayıcı](scheduler-class.md)) işi yürütmek için yürütme bağlamlarını kullanır için uygulamanız tarafından sıraya. Win32 iş parçacığı, Windows işletim sisteminde bir yürütme bağlamı örneğidir.  
  
 Herhangi bir zamanda bir Zamanlayıcının eşzamanlılık düzeyi kaynak yöneticisi tarafından kendisine verilen sanal işlemcilerin sayısına eşittir. Bir sanal işlemci için bir işlem kaynağı ve Haritalar ve alttaki sistemde bir donanım iş parçacığına bir soyutlamadır. Yalnızca tek bir zamanlayıcı bağlamı bir sanal işlemci üzerinde belirli bir zamanda çalıştırabilirsiniz.  
  
 Zamanlayıcı doğası gereği işbirliği yapan ile bir bekleme durumuna girmeyi isterse bir yürütme bağlamı herhangi bir zamanda sanal işlemcisini farklı bir bağlama sağlayabilir. Beklemesi karşılandığında, Zamanlayıcı kullanılabilir bir sanal işlemci onu yürütmeye başlayıncaya kadar devam edilemiyor.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Context`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="block"></a> Blok 

 Geçerli bağlamı engeller.  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.  
  
 Sanal işlemci çağıran bağlamını bir sanal işlemci üzerinde yürütülüyorsa, yürütme veya potansiyel olarak için başka bir çalıştırılabilir bağlam bulabilirsiniz yeni bir tane oluşturun.  
  
 Sonra `Block` yöntemi çağrıldıktan veya çağrılır, bunu bir çağrı ile eşleştirin gerekir [Engellemeyi Kaldır](#unblock) yöntemi sırayla yeniden çalıştırmak için başka bir yürütme bağlamı. Kodunuzu arayabilmesi için başka bir iş parçacığının kendi bağlamının yayımladığı noktası arasında bir kritik süre farkında olması `Unblock` yöntemi ve burada gerçek yöntemi çağrısında noktası `Block` yapılır. Bu süre boyunca hangi sırayla engelleyebilir veya engellemesini kendi nedeniyle (örneğin, bir kilit alınırken) herhangi bir yöntemi çağırmamalıdır. Çağrılar `Block` ve `Unblock` yöntemi yaptığını izlemek engelleme ve kaldırma nedeni. Yalnızca bir nesne sahipliğini olmalıdır bir `Block` -  `Unblock` çifti.  
  
 Bu yöntem, özel durumlar dahil olmak üzere, çeşitli oluşturabilecek [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md).  
  
##  <a name="dtor"></a> ~ Bağlamı 

```
virtual ~Context();
```  
  
##  <a name="currentcontext"></a> CurrentContext 

 Geçerli bağlama bir işaretçi döndürür.  
  
```
static Context* __cdecl CurrentContext();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.  
  
##  <a name="getid"></a> GetId 

 Bağlamın ait olduğu zamanlayıcıda benzersiz olan bağlam için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlamın ait olduğu zamanlayıcıda benzersiz olan bağlam için bir tanımlayıcı.  
  
##  <a name="getschedulegroupid"></a> GetScheduleGroupId 

 Bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetScheduleGroupId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin dönüş değeri bir anlık örnekleme bağlamın üzerinde yürütülmekte olduğu zamanlama grubu var. Bu yöntem, geçerli bağlamı dışındaki başka bir bağlamda çağrılırsa, değeri döndürülür ve bağlı yararlandı olamaz şu eski olabilir. Genellikle, bu yöntem, hata ayıklama veya yalnızca izleme için kullanılır.  
  
##  <a name="getvirtualprocessorid"></a> GetVirtualProcessorId 

 Bağlamın üzerinde yürütülmekte olduğu sanal işlemci için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlamı geçerli bağlamın üzerinde yürütülmekte olduğu sanal işlemci için bir tanımlayıcı sanal bir işlemci üzerinde yürütülüyorsa; Aksi takdirde, değeri `-1`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin dönüş değeri anlık bir bağlamın üzerinde yürütülmekte olduğu sanal işlemci örnekleme ' dir. Bu değer döndürülür ve bağlı yararlandı olamaz şu eski olabilir. Genellikle, bu yöntem, hata ayıklama veya yalnızca izleme için kullanılır.  
  
##  <a name="id"></a> Kimliği 

 Geçerli bağlamın ait olduğu zamanlayıcıda benzersiz olan geçerli bağlam için bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir Zamanlayıcı, geçerli bağlamın ait olduğu zamanlayıcıda benzersiz olan geçerli bağlam için bir tanımlayıcı bağlıysa, Aksi takdirde, değeri `-1`.  
  
##  <a name="iscurrenttaskcollectioncanceling"></a> Iscurrenttaskcollectioncanceling 

 Döndürür bir işaret olup geçerli bağlamda satır içi şu anda yürütülmekte olan görev koleksiyonunun etkin bir iptalin ortasında (veya kısa süre içinde olacaktır).  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir zamanlayıcı çağrı bağlamına bağlı olduğu ve bir görev grubu bu bağlamda bir görev satıriçi yürütüyor, bir gösterge olup bu görev grubu etkin bir iptalin ortasında (veya kısa süre içinde olacaktır); Aksi takdirde, değeri `false`.  
  
##  <a name="issynchronouslyblocked"></a> Issynchronouslyblocked 

 Bağlamın eş zamanlı olarak engellenip olup olmadığını belirler. Bir bağlam açıkça engellemeyle eylem gerçekleştirilen, zaman uyumlu olarak engellendiği kabul edilir.  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçerik olup olmadığını zaman uyumlu olarak engellenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bağlam açıkça engellemeyle eylem gerçekleştirilen, zaman uyumlu olarak engellendiği kabul edilir. İş parçacığı Zamanlayıcısı, bu doğrudan çağrı gösterir `Context::Block` yöntemi veya kullanılarak oluşturulmuş bir eşitleme nesnesi `Context::Block` yöntemi.  
  
 Bu yöntemin dönüş değeri bağlamın eş zamanlı olarak engellenip anlık bir örnektir. Bu değer döndürülür ve yalnızca belirli koşullarda kullanılabilir şu eski olabilir.  
  
##  <a name="operator_delete"></a> delete işleci 

 A `Context` nesne çalışma zamanı tarafından dahili olarak bozulur. Açıkça silinemez.  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>Parametreler  
*_PObject*<br/>
Silinecek nesnenin bir işaretçi.  
  
##  <a name="oversubscribe"></a> Oversubscribe 

 Bağlam, Zamanlayıcı içindeki sanal işlemcilerin birinde yürütülürken çağrıldığında kod bloğunun süresi için bir zamanlayıcıya ek bir sanal işlemci ekler.  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>Parametreler  
*_BeginOversubscription*<br/>
Varsa `true`, aşırı abonelik süresi boyunca bir ek sanal işlemci eklenmelidir göstergesidir. Varsa `false`, gecikmeyi bitmelidir ve önceden eklenmiş sanal işlemci kaldırılmalıdır göstergesidir.  
  
##  <a name="schedulegroupid"></a> ScheduleGroupId 

 Geçerli bağlamın üzerinde çalışmakta olduğu zamanlama grubu için bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir zamanlayıcı bağlı olduğu ve bir zamanlama grubu üzerinde çalışırken, Zamanlayıcı için bir tanımlayıcı grubu, geçerli bağlamın üzerinde çalışmakta olduğu; Aksi takdirde, değeri `-1`.  
  
##  <a name="unblock"></a> Engellemeyi Kaldır 

 Engellemesini kaldırır ve çalıştırılabilir duruma gelmesine neden olur.  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir çağrı için mükemmel bir şekilde yasal `Unblock` yöntemine yapılan çağrı ile önce gelmesi [blok](#block) yöntemi. Çağrıları sürece `Block` ve `Unblock` yöntemleri düzgün bir şekilde eşleştirilmiş, çalışma zamanı ya da sıralama, doğal yarışı düzgün bir şekilde işler. Bir `Unblock` çağrı önce gelen bir `Block` çağrı yalnızca etkisini `Block` çağırın.  
  
 Bu yöntemden atılan çeşitli özel durumlar vardır. Bir bağlam çağırmaya kalktığında `Unblock` yöntemi kendi üzerinde bir [context_self_unblock](context-self-unblock-class.md) özel durumu oluşturulur. Varsa çağrılar `Block` ve `Unblock` değil düzgün bir şekilde eşleştirilmiş (örneğin, iki için çağırdığı `Unblock` çalışmakta olan bir bağlamı için yapılan), [context_unblock_unbalanced](context-unblock-unbalanced-class.md) özel durumu oluşturulur.  
  
 Kodunuzu arayabilmesi için başka bir iş parçacığının kendi bağlamının yayımladığı noktası arasında bir kritik süre farkında olması `Unblock` yöntemi ve burada gerçek yöntemi çağrısında noktası `Block` yapılır. Bu süre boyunca hangi sırayla engelleyebilir veya engellemesini kendi nedeniyle (örneğin, bir kilit alınırken) herhangi bir yöntemi çağırmamalıdır. Çağrılar `Block` ve `Unblock` yöntemi yaptığını izlemek engelleme ve kaldırma nedeni. Yalnızca bir nesne sahipliğini olmalıdır bir `Block` ve `Unblock` çifti.  
  
##  <a name="virtualprocessorid"></a> Virtualprocessorıd 

 Geçerli bağlamın üzerinde yürütülmekte olduğu sanal işlemci için bir tanımlayıcı döndürür.  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bağlam için bir Zamanlayıcı, geçerli bağlamın üzerinde yürütülmekte olduğu sanal işlemci için bir tanımlayıcı bağlıysa, Aksi takdirde, değeri `-1`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin dönüş değeri, geçerli bağlamın üzerinde yürütülmekte olduğu sanal işlemci anlık bir örnekleme ' dir. Bu değer döndürülür ve bağlı yararlandı olamaz şu eski olabilir. Genellikle, bu yöntem, hata ayıklama veya yalnızca izleme için kullanılır.  
  
##  <a name="yield"></a> yield 

 Başka bir bağlamın çalıştırılabilmesi için yürütmeyi verir. Zamanlayıcı, başka bir bağlam için yield kullanılabilir haldeyse, başka bir işletim sistemi iş parçacığı verebilir.  
  
```
static void __cdecl Yield();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.  
  
##  <a name="yieldexecution"></a> YieldExecution 

 Başka bir bağlamın çalıştırılabilmesi için yürütmeyi verir. Zamanlayıcı, başka bir bağlam için yield kullanılabilir haldeyse, başka bir işletim sistemi iş parçacığı verebilir.  
  
```
static void __cdecl YieldExecution();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulan ve/veya şu anda çağrı bağlamla ilişkili hiçbir Zamanlayıcı ise çağrı bağlamına iliştirilemez. işlem varsayılan Zamanlayıcı neden olur.  
  
 Bu işlev, Visual Studio 2015'te yenidir ve aynıdır [Yield](#yield) çalışır ancak Windows.h Yield makroda ile çakışmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)   
 [Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




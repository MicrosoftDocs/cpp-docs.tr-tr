---
title: "structured_task_group sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs: C++
helpviewer_keywords: structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae2e4648e94d05edc3ec787232bab7f1db8aea90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="structuredtaskgroup-class"></a>structured_task_group Sınıfı
`structured_task_group` Sınıfı paralel iş yüksek oranda yapılandırılmış koleksiyonunu temsil eder. Tek tek Paralel Görevler sıraya bir `structured_task_group` kullanarak `task_handle` nesnelerini ve tamamlanmalarını bekleyin veya yürütme başlamıştır olmayan herhangi bir görevi iptal edilecek yürütme tamamlandı önce görev grubu iptal.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class structured_task_group;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[structured_task_group](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `structured_task_group` nesnesi.|  
|[~ structured_task_group yok Edicisi](#dtor)|Bozar bir `structured_task_group` nesnesi. Ya da çağrı beklenir `wait` veya `run_and_wait` yıkıcı yürütmeden önce nesnesi üzerinde yöntemi yıkıcı yürütülmekte olduğu sürece sonucu olarak yığın bir özel durum nedeniyle geriye doğru izleme.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[İptal](#cancel)|Alt ağaç görev grup kökü iş iptal edilmesi girişimi en iyi çaba yapar. Görev grubu olarak zamanlanan her görev geçişli mümkünse iptal.|  
|[is_canceling](#is_canceling)|Arayan olsun veya olmasın görevi şu anda iptal ortasında grubudur bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `structured_task_group` nesne (gibi kesinlikle döndürmek için bu yöntemi niteleyen rağmen `true`). Bu durumda olabilir, `structured_task_group` nesne satır içi yürütme ve başka bir görev grubu yukarı iş ağacında iptal edildi. Bu where gibi durumlarda çalışma zamanı iptal bu akar önceden belirleyebilirsiniz `structured_task_group` nesnesi `true` de döndürülür.|  
|[çalıştırma](#run)|Fazla Yüklendi. Üzerinde bir görev zamanlar `structured_task_group` nesnesi. Arayan ömrü yönetir `task_handle` nesnesi geçirildi `_Task_handle` parametresi. Parametresi alan sürüm `_Placement` görev o parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.|  
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Satır içi Yardımı ile arama bağlamda çalıştırılmak üzere bir görev zamanlar `structured_task_group` tam iptal desteği için nesne. Varsa bir `task_handle` nesnesini parametre olarak geçirilen `run_and_wait`, çağıran ömrü yönetilmesinden sorumludur `task_handle` nesnesi. İşlev, ardından tüm çalıştığı bekler `structured_task_group` nesne tamamlandı ya da iptal edildi.|  
|[bekleme](#wait)|Tüm çalıştığı bekler `structured_task_group` tamamlanan veya iptal edildi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dizi kullanıma yerleştirilen ciddi kısıtlamaları vardır bir `structured_task_group` nesne performans sağlamak için:  
  
-   Tek bir `structured_task_group` nesne birden çok iş parçacığı tarafından kullanılamaz. Tüm işlemler bir `structured_task_group` nesnesi nesne oluşturulan iş parçacığı tarafından gerçekleştirilmesi gerekir. Bu kural için iki özel durum üye işlevleri olan `cancel` ve `is_canceling`. Nesne bir lambda ifadesi yakalama listesinde olmayabilir ve görev iptali işlemlerden birini kullanmadığınız sürece bir görev içinde kullanılması.  
  
-   Tüm görevler için zamanlanmış bir `structured_task_group` nesnesi kullanılarak zamanlanır `task_handle` nesneleri hangi ömrü açıkça yönetmeniz gerekir.  
  
-   Birden çok grubu yalnızca kesinlikle iç içe geçmiş sırada kullanılabilir. İki `structured_task_group` nesneleri bildirildiğinde, (iç bir) bildirilen ikincisi dışında herhangi bir yöntemini önce destruct gerekir `cancel` veya `is_canceling` Birincisi olarak adlandırılır (dış bir). Bu durum, yalnızca birden çok bildirme her iki durumda da geçerlidir `structured_task_group` için sıraya alınması ile bir görev durumunun yanı sıra, aynı ya da işlevsel olarak iç içe geçmiş kapsamlar nesnelerinde `structured_task_group` aracılığıyla `run` veya `run_and_wait` yöntemleri.  
  
-   Genel aksine `task_group` sınıfı, tüm durumlarda `structured_task_group` sınıfı son. Grup görevlere sıraya alındı ve tamamlanmalarını beklenen sonra aynı gruba yeniden kullanamazsınız.  
  
 Daha fazla bilgi için bkz: [görev Paralelliği](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `structured_task_group`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="cancel"></a>İptal 

 Alt ağaç görev grup kökü iş iptal edilmesi girişimi en iyi çaba yapar. Görev grubu olarak zamanlanan her görev geçişli mümkünse iptal.  
  
```
void cancel();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="is_canceling"></a>is_canceling 

 Arayan olsun veya olmasın görevi şu anda iptal ortasında grubudur bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `structured_task_group` nesne (gibi kesinlikle döndürmek için bu yöntemi niteleyen rağmen `true`). Bu durumda olabilir, `structured_task_group` nesne satır içi yürütme ve başka bir görev grubu yukarı iş ağacında iptal edildi. Bu where gibi durumlarda çalışma zamanı iptal bu akar önceden belirleyebilirsiniz `structured_task_group` nesnesi `true` de döndürülür.  
  
```
bool is_canceling();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Göstergesidir olup `structured_task_group` nesne ortasında iptal (ya da kısa süre içinde olması garanti).  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [iptal](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="run"></a>çalıştırma 

 Üzerinde bir görev zamanlar `structured_task_group` nesnesi. Arayan ömrü yönetir `task_handle` nesnesi geçirildi `_Task_handle` parametresi. Parametresi alan sürüm `_Placement` görev o parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.  
  
```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Görev tanıtıcı gövdesi yürütmek için çağrılan işlev nesnesi türü.  
  
 `_Task_handle`  
 Planlanan iş için bir tanıtıcı. Çağıranın bu nesne ömrü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `wait` veya `run_and_wait` yönteminin çağrılıp çağrılmadığını bu `structured_task_group` nesnesi.  
  
 `_Placement`  
 Burada görev temsil ettiği konum başvuru `_Task_handle` parametre yürütün.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı bu yöntemine geçirdiğiniz çalışma işlevini bir kopyasını oluşturur. Bu yönteme geçirin işlevi nesnesindeki gerçekleşen durumu değişiklikleri bu işlev nesnesi kopyanızda görünmez.  
  
 Varsa `structured_task_group` destructs yığını öğesinden bir özel durum geriye doğru izleme sonucunda gerektirmeyen bir çağrı olarak yapılmadığını güvence altına almak `wait` veya `run_and_wait` yöntemi. Bu durumda, yıkıcı uygun şekilde iptal etmek ve tarafından temsil edilen görev bekleyin `_Task_handle` tamamlamak için parametre.  
  
 Oluşturur bir [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) görev işlemek, özel durum tarafından verilen `_Task_handle` parametresi zaten zamanlandı görev grup nesnesi üzerine `run` yöntemi ve hiçbir müdahalede bulunan çağrısına açıldı ya da `wait` veya `run_and_wait` bu görev grubunda yöntemi.  
  
##  <a name="run_and_wait"></a>run_and_wait 

 Satır içi Yardımı ile arama bağlamda çalıştırılmak üzere bir görev zamanlar `structured_task_group` tam iptal desteği için nesne. Varsa bir `task_handle` nesnesini parametre olarak geçirilen `run_and_wait`, çağıran ömrü yönetilmesinden sorumludur `task_handle` nesnesi. İşlev, ardından tüm çalıştığı bekler `structured_task_group` nesne tamamlandı ya da iptal edildi.  
  
```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Görevi çalıştırmak için çağrılan işlev nesnesi türü.  
  
 `_Task_handle`  
 Satır içi arama bağlamda çalıştırılacak görev için bir tanıtıcı. Çağıranın bu nesne ömrü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `run_and_wait` yöntemi yürütme biter.  
  
 `_Func`  
 İş gövdesi çağrılacak çağrılacak işlev. Bu bir lambda veya işlev çağırma işleci imzalı bir sürümünü destekleyen başka bir nesne olabilir `void operator()()`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup bekleme yerine getirildiği bir gösterge veya görev grubu, bir açık İptal işlemi veya görevlerinin birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için bkz: [task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla için zamanlanmış görevler Not `structured_task_group` nesne satır içi arama bağlamda yürütme.  
  
 Bir veya daha fazlası için Zamanlanmış Görevler'in `structured_task_group` nesne bir özel durum oluşturur, çalışma zamanı kendi seçme bir tür özel durumu seçin ve çağrısı dışında yayılması `run_and_wait` yöntemi.  
  
 Bu işlev döndükten sonra `structured_task_group` nesne bir son duruma olarak kabul edilir ve kullanılmamalıdır. Sonra bu kullanımı Not `run_and_wait` yöntemi döndürür tanımsız davranışa neden olur.  
  
 Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için bir zorunluluğuna sahip veya `wait` yöntemi yıkıcısı önce `structured_task_group` yürütür.  
  
##  <a name="ctor"></a>structured_task_group 

 Yeni bir oluşturur `structured_task_group` nesnesi.  
  
```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```  
  
### <a name="parameters"></a>Parametreler  
 `_CancellationToken`  
 Bu yapılandırılmış görev grubuyla ilişkilendirilecek bir iptal belirteci. Yapılandırılmış görev grup belirteci iptal edildiğinde iptal edilecek.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir iptal belirteci alan oluşturucu oluşturur bir `structured_task_group` , iptal edilecek belirteçle ilişkili kaynak iptal ettiğinizde. Bir açık iptal belirteci sağlama örtük bir iptal belirteci yok ya da farklı bir belirteci ile üst gruptan katılan bu yapılandırılmış görev grubunun yalıtır.  
  
##  <a name="dtor"></a>~ structured_task_group 

 Bozar bir `structured_task_group` nesnesi. Ya da çağrı beklenir `wait` veya `run_and_wait` yıkıcı yürütmeden önce nesnesi üzerinde yöntemi yıkıcı yürütülmekte olduğu sürece sonucu olarak yığın bir özel durum nedeniyle geriye doğru izleme.  
  
```
~structured_task_group();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi normal yürütme (bir özel durum nedeniyle yığını geriye doğru izleme gibi değil) ve, sonuç olarak çalışıyorsa `wait` ya da `run_and_wait` yöntemleri adlı, yıkıcı atabilir bir [missing_wait](missing-wait-class.md) özel durum.  
  
##  <a name="wait"></a>bekleme 

 Tüm çalıştığı bekler `structured_task_group` tamamlanan veya iptal edildi.  
  
```
task_group_status wait();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup bekleme yerine getirildiği bir gösterge veya görev grubu, bir açık İptal işlemi veya görevlerinin birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için bkz: [task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla için zamanlanmış görevler Not `structured_task_group` nesne satır içi arama bağlamda yürütme.  
  
 Bir veya daha fazlası için Zamanlanmış Görevler'in `structured_task_group` nesne bir özel durum oluşturur, çalışma zamanı kendi seçme bir tür özel durumu seçin ve çağrısı dışında yayılması `wait` yöntemi.  
  
 Bu işlev döndükten sonra `structured_task_group` nesne bir son duruma olarak kabul edilir ve kullanılmamalıdır. Sonra bu kullanımı Not `wait` yöntemi döndürür tanımsız davranışa neden olur.  
  
 Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için bir zorunluluğuna sahip veya `run_and_wait` yöntemi yıkıcısı önce `structured_task_group` yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [task_group sınıfı](task-group-class.md)   
 [task_handle Sınıfı](task-handle-class.md)

---
title: task_group sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
dev_langs:
- C++
helpviewer_keywords:
- task_group class
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7ee8fa674174d95c3e538889f6d5538be049b70
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020726"
---
# <a name="taskgroup-class"></a>task_group Sınıfı
`task_group` Sınıf beklenen veya iptal edilen paralel iş koleksiyonunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class task_group;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[task_group](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `task_group` nesne.|  
|[~ task_group yok Edicisi](#dtor)|Yok eder bir `task_group` nesne. Çağırın ya da beklenir `wait` veya `run_and_wait` yok Edicisi sonucunda, bir özel durum nedeniyle geriye doğru izleme yığın Yürütülüyor sürece yok Edicisi, yürütmeden önce nesnesi üzerinde yöntemi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[İptal](#cancel)|Alt ağaç bu görev grubu kökü çalışmanın iptal edilmesi girişimi bir en iyi hale getirir. Her görev, görev grubuna zamanlanmış geçişli mümkünse iptal.|  
|[is_canceling](#is_canceling)|Çağıranın olup olmadığını görev grubunu iptal ortasında şu anda olduğunu bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `task_group` nesne (kesinlikle niteleyen gibi döndürmek için bu yöntem olsa da `true`). Bu durum olabilir, `task_group` nesne satır içi yürütme ve başka bir görev grubu oluşturan iş ağacında iptal edildi. Bu nerede gibi durumlarda çalışma zamanı iptal bu akar vaktinden belirleyebilirsiniz `task_group` nesnesi `true` da döndürülür.|  
|[Çalıştırma](#run)|Fazla Yüklendi. Üzerinde bir görevi zamanlar `task_group` nesne. Varsa bir `task_handle` nesnesi bir parametre olarak geçirilir `run`, ömrünü yönetmek için çağıran sorumludur `task_handle` nesne. Yığın ayırma olabilen çalışma zamanı içinde bir parametre içerir yönteminin bir işlev nesnesine bir başvuru alan sürümünü gerçekleştirmek için bir başvuru alan sürümü kullanmaktan daha az iyi bir `task_handle` nesne. Parametre alan sürüm `_Placement` görevi bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.|  
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Satır içi arama bağlamda Yardımı ile çalışması için bir görevi zamanlar `task_group` tam iptal desteği için nesne. İşlevi, ardından tüm çalıştığı bekler `task_group` nesne tamamlandı veya iptal edildi. Varsa bir `task_handle` nesnesi bir parametre olarak geçirilir `run_and_wait`, ömrünü yönetmek için çağıran sorumludur `task_handle` nesne.|  
|[bekleme](#wait)|Tüm çalıştığı bekler `task_group` nesne tamamlandı veya iptal edildi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yoğun kısıtlı aksine `structured_task_group` sınıfı `task_group` daha genel yapısı bir sınıftır. Herhangi bir kısıtlama tarafından açıklanan yok [structured_task_group](structured-task-group-class.md). `task_group` nesneleri güvenli bir şekilde iş parçacıkları arasında kullanılabilir ve serbest biçimli yollarla kullanılan. Dezavantajı `task_group` yapıdır değil gerçekleştirebilir ve `structured_task_group` küçük miktarda iş gerçekleştirmek için Görevler oluşturun.  
  
 Daha fazla bilgi için [görev Paralelliği](../task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `task_group`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="cancel"></a> İptal 

 Alt ağaç bu görev grubu kökü çalışmanın iptal edilmesi girişimi bir en iyi hale getirir. Her görev, görev grubuna zamanlanmış geçişli mümkünse iptal.  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [iptal](../cancellation-in-the-ppl.md).  
  
##  <a name="is_canceling"></a> is_canceling 

 Çağıranın olup olmadığını görev grubunu iptal ortasında şu anda olduğunu bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `task_group` nesne (kesinlikle niteleyen gibi döndürmek için bu yöntem olsa da `true`). Bu durum olabilir, `task_group` nesne satır içi yürütme ve başka bir görev grubu oluşturan iş ağacında iptal edildi. Bu nerede gibi durumlarda çalışma zamanı iptal bu akar vaktinden belirleyebilirsiniz `task_group` nesnesi `true` da döndürülür.  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir gösterge olup `task_group` nesne ortasında iptal (veya kısa süre içinde olması sağlanır).  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [iptal](../cancellation-in-the-ppl.md).  
  
##  <a name="run"></a> Çalıştırma 

 Üzerinde bir görevi zamanlar `task_group` nesne. Varsa bir `task_handle` nesnesi bir parametre olarak geçirilir `run`, ömrünü yönetmek için çağıran sorumludur `task_handle` nesne. Yığın ayırma olabilen çalışma zamanı içinde bir parametre içerir yönteminin bir işlev nesnesine bir başvuru alan sürümünü gerçekleştirmek için bir başvuru alan sürümü kullanmaktan daha az iyi bir `task_handle` nesne. Parametre alan sürüm `_Placement` görevi bu parametre tarafından belirtilen konumda yürütme doğru güçlü eğilimi nedeniyle neden olur.  
  
```  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func  
);  
  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func,  
   location& _Placement  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle,  
   location& _Placement  
);  
```  
  
### <a name="parameters"></a>Parametreler  
*_Function*<br/>
Görev tanıtıcısını gövdesi yürütme için çağrılacak işlev nesnesinin türü.  
  
*_Func*<br/>
Görevin çağırmak için çağrılacak işlev. Bu bir lambda ifadesi veya işlev çağrısı işleci imzalı sürümünü destekleyen başka bir nesneyi olabilir `void operator()()`.  
  
*Y_erleştirme*<br/>
Görevi nerede temsil ettiği konumuna yönelik bir başvuru `_Func` parametre yürütün.  
  
*_Task_handle*<br/>
Zamanlanmış iş için bir tanıtıcı. Çağıranın bu nesnenin ömrünü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `wait` veya `run_and_wait` bu yöntemi çağrıldıktan `task_group` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı, sonra çağıran işlevin verir olabilen daha sonraki bir zamanda, çalıştırmak için sağlanan çalışma işlevi zamanlar. Bu yöntemde bir [task_handle](task-handle-class.md) sağlanan çalışma işlevi bir kopyasını tutacak nesne. Bu nedenle, bu yönteme geçirin bir işlev nesnesi içinde gerçekleşen durumu değişiklikleri, bu işlev nesnesi kopyanızda görünmez. Ayrıca, iş işlev dönene kadar işaretçi veya başvuruya iş işleve göre geçirdiğiniz tüm nesnelerin ömrünü geçerli kalır emin olun.  
  
 Varsa `task_group` destructs yığını bir özel durumdan geriye doğru izleme sonucu olarak, gerekmez çağrı olarak yapıldığını garanti `wait` veya `run_and_wait` yöntemi. Bu durumda, yok edici uygun şekilde iptal edip tarafından temsil edilen bir görevi beklerken `_Task_handle` tamamlamak için parametre.  
  
 Çağırılıyorsa yöntem bir [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) görev işleme özel durum tarafından verilen `_Task_handle` parametresi zaten zamanlandı bir görev grubu nesnesi üzerine `run` yöntemi ve olmuştur yok bölen çağrı tersini belirtmediği için ya da `wait` veya `run_and_wait` bu görev grubunda yöntemi.  
  
##  <a name="run_and_wait"></a> run_and_wait 

 Satır içi arama bağlamda Yardımı ile çalışması için bir görevi zamanlar `task_group` tam iptal desteği için nesne. İşlevi, ardından tüm çalıştığı bekler `task_group` nesne tamamlandı veya iptal edildi. Varsa bir `task_handle` nesnesi bir parametre olarak geçirilir `run_and_wait`, ömrünü yönetmek için çağıran sorumludur `task_handle` nesne.  
  
```  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   const _Function& _Func  
);  
```  
  
### <a name="parameters"></a>Parametreler  
*_Function*<br/>
Görevin yürütmek için çağrılacak işlev nesnesinin türü.  
  
*_Task_handle*<br/>
Satır içi arama bağlamda çalıştırılacak görev için bir tanıtıcı. Çağıranın bu nesnenin ömrünü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `run_and_wait` yöntemi yürütme biter.  
  
*_Func*<br/>
İş gövdesi çağırmak için çağrılacak işlev. Bu bir lambda ifadesi veya işlev çağrısı işleci imzalı sürümünü destekleyen başka bir nesneyi olabilir `void operator()()`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir gösterge olup bekleme memnun ettiyse veya görev grubu, bir açık İptal işlemi veya görevleri birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için [task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazlası için zamanlanmış görevleri Not `task_group` nesne satır içi arama bağlamda yürütme.  
  
 Bir veya daha fazlası için zamanlanmış görevlerin `task_group` nesnesi, bir özel durum oluşturursa, çalışma zamanı kendi seçtiğiniz bir tür özel durumu seçin ve çağrı dışına yayan `run_and_wait` yöntemi.  
  
 Geri döndürme işlevi üzerine `run_and_wait` metodunda bir `task_group` nesnesi, çalışma zamanı nesne Burada, yeniden kullanılabilir bir temiz durumuna sıfırlar. Bu durum içerir burada `task_group` nesnesi iptal edildi.  
  
 Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için olan uyumluluğunu doğrulamıştır olması veya `wait` yöntemi yok edicisinde önce `task_group` yürütür.  
  
##  <a name="ctor"></a> task_group 

 Yeni bir oluşturur `task_group` nesne.  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>Parametreler  
*_CancellationToken*<br/>
Bu görev grubu ile ilişkilendirilecek iptal belirteci. Belirteç iptal edildiğinde görev grubunu iptal edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 İptali belirteci alan oluşturucu bir `task_group` , iptal edilemez belirteçle ilişkili kaynak iptal edildiğinde. Bir açık bir iptal belirteci sağlayan örtük bir iptal belirteci yok ya da farklı bir belirteç ile bir üst gruptan katılan bu görev grubunun yalıtır.  
  
##  <a name="dtor"></a> ~ task_group 

 Yok eder bir `task_group` nesne. Çağırın ya da beklenir `wait` veya `run_and_wait` yok Edicisi sonucunda, bir özel durum nedeniyle geriye doğru izleme yığın Yürütülüyor sürece yok Edicisi, yürütmeden önce nesnesi üzerinde yöntemi.  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok edici normal yürütmenin (bir özel durum nedeniyle yığını geriye doğru izleme gibi değil) ve birinin diğerinden sonucu olarak çalışıyorsa `wait` ya da `run_and_wait` yöntemi çağrılır, yok edici oluşturabilecek bir [missing_wait](missing-wait-class.md) özel durum.  
  
##  <a name="wait"></a> bekleme 

 Tüm çalıştığı bekler `task_group` nesne tamamlandı veya iptal edildi.  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir gösterge olup bekleme memnun ettiyse veya görev grubu, bir açık İptal işlemi veya görevleri birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için [task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazlası için zamanlanmış görevleri Not `task_group` nesne satır içi arama bağlamda yürütme.  
  
 Bir veya daha fazlası için zamanlanmış görevlerin `task_group` nesnesi, bir özel durum oluşturursa, çalışma zamanı kendi seçtiğiniz bir tür özel durumu seçin ve çağrı dışına yayan `wait` yöntemi.  
  
 Çağırma `wait` üzerinde bir `task_group` nesne Burada, yeniden kullanılabilir bir temiz durumuna sıfırlar. Bu durum içerir burada `task_group` nesnesi iptal edildi.  
  
 Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için olan uyumluluğunu doğrulamıştır olması veya `run_and_wait` yöntemi yok edicisinde önce `task_group` yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [structured_task_group sınıfı](structured-task-group-class.md)   
 [task_handle Sınıfı](task-handle-class.md)
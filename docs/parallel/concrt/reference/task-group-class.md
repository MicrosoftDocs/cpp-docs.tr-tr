`task_group` Sınıfı beklenen veya iptal edilen paralel iş koleksiyonunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class task_group;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[task_group](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `task_group` nesnesi.|  
|[~ task_group yok Edicisi](#dtor)|Bozar bir `task_group` nesnesi. Ya da çağrı beklenir `wait` veya `run_and_wait` yıkıcı sonucunda yığını bir özel durum nedeniyle geriye doğru izleme, yürütülmekte olduğu sürece yıkıcı, yürütmeden önce nesnesi üzerinde yöntemi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[İptal](#cancel)|Alt ağaç görev grup kökü iş iptal edilmesi girişimi en iyi çaba yapar. Görev grubu olarak zamanlanan her görev geçişli mümkünse iptal.|  
|[is_canceling](#is_canceling)|Arayan olsun veya olmasın görevi şu anda iptal ortasında grubudur bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `task_group` nesne (gibi kesinlikle döndürmek için bu yöntemi niteleyen rağmen `true`). Bu durumda olabilir, `task_group` nesne satır içi yürütme ve başka bir görev grubu yukarı iş ağacında iptal edildi. Bu where gibi durumlarda çalışma zamanı iptal bu akar önceden belirleyebilirsiniz `task_group` nesnesi `true` de döndürülür.|  
|[çalıştırma](#run)|Fazla Yüklendi. Üzerinde bir görev zamanlar `task_group` nesnesi. Varsa bir `task_handle` nesnesini parametre olarak geçirilen `run`, çağıran ömrü yönetilmesinden sorumludur `task_handle` nesnesi. Yığın ayırma olabilen çalışma zamanı içindeki bir parametre içermesidir işlevi nesneye bir başvurusu alan metodunun sürümü gerçekleştirmek için bir başvuru alır sürümü kullanmaktan daha az iyi bir `task_handle` nesnesi. Parametre alan sürüm `_Placement` görev o parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.|  
|[run_and_wait](#run_and_wait)|Fazla Yüklendi. Satır içi Yardımı ile arama bağlamda çalıştırılmak üzere bir görev zamanlar `task_group` tam iptal desteği için nesne. İşlev, ardından tüm çalıştığı bekler `task_group` nesne tamamlandı ya da iptal edildi. Varsa bir `task_handle` nesnesini parametre olarak geçirilen `run_and_wait`, çağıran ömrü yönetilmesinden sorumludur `task_handle` nesnesi.|  
|[bekleme](#wait)|Tüm çalıştığı bekler `task_group` nesne tamamlandı ya da iptal edildi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yoğun kısıtlı aksine `structured_task_group` sınıfı, `task_group` çok daha genel yapısı bir sınıftır. Tarafından tanımlanan kısıtlamalara hiçbirini yok [structured_task_group](structured-task-group-class.md). `task_group`nesneleri güvenle iş parçacıkları arasında kullanılır ve serbest biçimli yollarla kullanılan. Dezavantajı `task_group` yapıdır değil gerçekleştirebilir yanı sıra `structured_task_group` iş küçük miktarda gerçekleştirmek için Görevler oluşturun.  
  
 Daha fazla bilgi için bkz: [görev Paralelliği](../task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `task_group`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="cancel"></a>İptal 

 Alt ağaç görev grup kökü iş iptal edilmesi girişimi en iyi çaba yapar. Görev grubu olarak zamanlanan her görev geçişli mümkünse iptal.  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [iptal](../cancellation-in-the-ppl.md).  
  
##  <a name="is_canceling"></a>is_canceling 

 Arayan olsun veya olmasın görevi şu anda iptal ortasında grubudur bildirir. Bu, gelmeyebilir `cancel` yöntemi çağrıldı `task_group` nesne (gibi kesinlikle döndürmek için bu yöntemi niteleyen rağmen `true`). Bu durumda olabilir, `task_group` nesne satır içi yürütme ve başka bir görev grubu yukarı iş ağacında iptal edildi. Bu where gibi durumlarda çalışma zamanı iptal bu akar önceden belirleyebilirsiniz `task_group` nesnesi `true` de döndürülür.  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Göstergesidir olup `task_group` nesne ortasında iptal (ya da kısa süre içinde olması garanti).  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [iptal](../cancellation-in-the-ppl.md).  
  
##  <a name="run"></a>çalıştırma 

 Üzerinde bir görev zamanlar `task_group` nesnesi. Varsa bir `task_handle` nesnesini parametre olarak geçirilen `run`, çağıran ömrü yönetilmesinden sorumludur `task_handle` nesnesi. Yığın ayırma olabilen çalışma zamanı içindeki bir parametre içermesidir işlevi nesneye bir başvurusu alan metodunun sürümü gerçekleştirmek için bir başvuru alır sürümü kullanmaktan daha az iyi bir `task_handle` nesnesi. Parametre alan sürüm `_Placement` görev o parametresi tarafından belirtilen konumda yürütme doğrultusunda ağırlıklı neden olur.  
  
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
 `_Function`  
 Görev tanıtıcı gövdesi yürütmek için çağrılan işlev nesnesi türü.  
  
 `_Func`  
 Görev gövdesi çağrılacak çağrılacak işlev. Bu bir lambda ifadesi veya bir işlev çağırma işleci imzalı sürümünü destekleyen başka bir nesne olabilir `void operator()()`.  
  
 `_Placement`  
 Burada görev temsil ettiği konum başvuru `_Func` parametre yürütün.  
  
 `_Task_handle`  
 Planlanan iş için bir tanıtıcı. Çağıranın bu nesne ömrü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `wait` veya `run_and_wait` yönteminin çağrılıp çağrılmadığını bu `task_group` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı arama işlevi döndükten sonra olabilen daha sonraki bir zamanda, çalıştırmak için sağlanan çalışma işlevi zamanlar. Bu yöntem bir [task_handle](task-handle-class.md) sağlanan çalışma işlevi bir kopyasını tutmak için nesne. Bu nedenle, bu yönteme geçirin işlevi nesnesindeki gerçekleşen durumu değişiklikleri bu işlev nesnesi kopyanızda görünmez. Ayrıca, iş işlev döndürünceye kadar işaretçi veya iş işlev başvurusunu tarafından geçirdiğiniz herhangi bir nesne ömrü geçerli olarak kaldıklarından emin olun.  
  
 Varsa `task_group` destructs yığını öğesinden bir özel durum geriye doğru izleme sonucunda gerektirmeyen bir çağrı olarak yapılmadığını güvence altına almak `wait` veya `run_and_wait` yöntemi. Bu durumda, yıkıcı uygun şekilde iptal etmek ve tarafından temsil edilen görev bekleyin `_Task_handle` tamamlamak için parametre.  
  
 Yöntem oluşturulur bir [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) görev işlemek, özel durum tarafından verilen `_Task_handle` parametresi zaten zamanlandı görev grup nesnesi üzerine `run` yöntemi ve yapılmış yok araya giren çağırmak için her iki `wait` veya `run_and_wait` bu görev grubunda yöntemi.  
  
##  <a name="run_and_wait"></a>run_and_wait 

 Satır içi Yardımı ile arama bağlamda çalıştırılmak üzere bir görev zamanlar `task_group` tam iptal desteği için nesne. İşlev, ardından tüm çalıştığı bekler `task_group` nesne tamamlandı ya da iptal edildi. Varsa bir `task_handle` nesnesini parametre olarak geçirilen `run_and_wait`, çağıran ömrü yönetilmesinden sorumludur `task_handle` nesnesi.  
  
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
 `_Function`  
 Görev gövdesi yürütmek için çağrılan işlev nesnesi türü.  
  
 `_Task_handle`  
 Satır içi arama bağlamda çalıştırılacak görev için bir tanıtıcı. Çağıranın bu nesne ömrü sorumluluğunu olduğuna dikkat edin. Çalışma zamanı kadar Canlı beklediğiniz devam edecek `run_and_wait` yöntemi yürütme biter.  
  
 `_Func`  
 İş gövdesi çağrılacak çağrılacak işlev. Bu bir lambda ifadesi veya bir işlev çağırma işleci imzalı sürümünü destekleyen başka bir nesne olabilir `void operator()()`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup bekleme yerine getirildiği bir gösterge veya görev grubu, bir açık İptal işlemi veya görevlerinin birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için bkz: [task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla için zamanlanmış görevler Not `task_group` nesne satır içi arama bağlamda yürütme.  
  
 Bir veya daha fazlası için Zamanlanmış Görevler'in `task_group` nesne bir özel durum oluşturur, çalışma zamanı kendi seçme bir tür özel durumu seçin ve çağrısı dışında yayılması `run_and_wait` yöntemi.  
  
 Dönüş bağlı `run_and_wait` yöntemi bir `task_group` nesnesi, çalışma zamanı nesne burada onu yeniden kullanılabilir bir temiz durumuna sıfırlar. Bu durum içerir nerede `task_group` nesne iptal edildi.  
  
 Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için bir zorunluluğuna sahip veya `wait` yöntemi yıkıcısı önce `task_group` yürütür.  
  
##  <a name="ctor"></a>task_group 

 Yeni bir oluşturur `task_group` nesnesi.  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_CancellationToken`  
 Bu görev grubuyla ilişkilendirilecek bir iptal belirteci. Belirteci iptal edildiğinde görev grubu iptal edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir iptal belirteci alan oluşturucu oluşturur bir `task_group` , iptal edilecek belirteçle ilişkili kaynak iptal ettiğinizde. Bir açık iptal belirteci sağlama örtük bir iptal belirteci yok ya da farklı bir belirteci ile üst gruptan katılan bu görev grubunun yalıtır.  
  
##  <a name="dtor"></a>~ task_group 

 Bozar bir `task_group` nesnesi. Ya da çağrı beklenir `wait` veya `run_and_wait` yıkıcı sonucunda yığını bir özel durum nedeniyle geriye doğru izleme, yürütülmekte olduğu sürece yıkıcı, yürütmeden önce nesnesi üzerinde yöntemi.  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi normal yürütme (bir özel durum nedeniyle yığını geriye doğru izleme gibi değil) ve, sonuç olarak çalışıyorsa `wait` ya da `run_and_wait` yöntemleri adlı, yıkıcı atabilir bir [missing_wait](missing-wait-class.md) özel durum.  
  
##  <a name="wait"></a>bekleme 

 Tüm çalıştığı bekler `task_group` nesne tamamlandı ya da iptal edildi.  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olup bekleme yerine getirildiği bir gösterge veya görev grubu, bir açık İptal işlemi veya görevlerinin birinden oluşturulan bir özel durum nedeniyle iptal edildi. Daha fazla bilgi için bkz: [task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla için zamanlanmış görevler Not `task_group` nesne satır içi arama bağlamda yürütme.  
  
 Bir veya daha fazlası için Zamanlanmış Görevler'in `task_group` nesne bir özel durum oluşturur, çalışma zamanı kendi seçme bir tür özel durumu seçin ve çağrısı dışında yayılması `wait` yöntemi.  
  
 Çağırma `wait` üzerinde bir `task_group` nesne burada onu yeniden kullanılabilir bir temiz durumuna sıfırlar. Bu durum içerir nerede `task_group` nesne iptal edildi.  
  
 Yürütme özel durumlu olmayan yolunda ya da bu yöntemi çağırmak için bir zorunluluğuna sahip veya `run_and_wait` yöntemi yıkıcısı önce `task_group` yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [structured_task_group sınıfı](structured-task-group-class.md)   
 [task_handle sınıfı](task-handle-class.md)
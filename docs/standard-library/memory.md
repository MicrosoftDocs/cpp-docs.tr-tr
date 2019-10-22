---
title: '&lt;memory &gt;'
ms.date: 08/04/2019
f1_keywords:
- memory/std::<memory>
- <memory>
- std::<memory>
helpviewer_keywords:
- memory header
ms.openlocfilehash: 4a6383ee94d021373b984122926a5bb73e18f953
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689361"
---
# <a name="ltmemorygt"></a>&lt;memory &gt;

Bir sınıfı, işleci ve nesneleri ayırmaya ve serbest bırakmaya yardımcı çeşitli şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<memory >

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[AddressOf](../standard-library/memory-functions.md#addressof)|Bir nesnenin doğru adresini alır.|
|[align](../standard-library/memory-functions.md#align)|Sağlanan hizalama ve başlangıç adresini temel alarak belirli bir boyut aralığı için bir işaretçi döndürür.|
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Belirtilen bir ayırıcıyla verilen tür için ayrılan ve oluşturulan nesnelere bir `shared_ptr` oluşturur.|
|[atomic_compare_exchange_strong](../standard-library/memory-functions.md#atomic_compare_exchange_strong)||
|[atomic_compare_exchange_weak](../standard-library/memory-functions.md#atomic_compare_exchange_weak)||
|[atomic_compare_exchange_strong_explicit](../standard-library/memory-functions.md#atomic_compare_exchange_strong_explicit)||
|[atomic_compare_exchange_weak_explicit](../standard-library/memory-functions.md#atomic_compare_exchange_weak_explicit)||
|[atomic_exchange](../standard-library/memory-functions.md#atomic_exchange)||
|[atomic_exchange_explicit](../standard-library/memory-functions.md#atomic_exchange_explicit)||
|[atomic_is_lock_free](../standard-library/memory-functions.md#atomic_is_lock_free)||
|[atomic_load](../standard-library/memory-functions.md#atomic_load)||
|[atomic_load_explicit](../standard-library/memory-functions.md#atomic_load_explicit)||
|[atomic_store](../standard-library/memory-functions.md#atomic_store)||
|[atomic_store_explicit](../standard-library/memory-functions.md#atomic_store_explicit)||
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|@No__t_0 için const cast.|
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Belirli bir adreste başlayan ve belirtilen blok boyutu içinde kalan karakterlerin izlenebilir işaretçi içermediğini atık toplayıcıya bildirir.|
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.|
|[default_delete](../standard-library/memory-functions.md#default_delete)|@No__t_0 ile ayrılmış nesneleri siler. @No__t_0 ile kullanım için uygun.|
|[destroy_at](../standard-library/memory-functions.md#destroy_at)|Toplu `destroy` yöntemi.|
|[kaldırılır](../standard-library/memory-functions.md#destroy)|Toplu `destroy` yöntemi.|
|[destroy_n](../standard-library/memory-functions.md#destroy_n)|Toplu `destroy` yöntemi.|
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|@No__t_0 için dinamik atama.|
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|@No__t_0 silici alın.|
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.|
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Belirli sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.|
|[make_shared](../standard-library/memory-functions.md#make_shared)|Varsayılan ayırıcıyı kullanarak sıfır veya daha fazla bağımsız değişkenle oluşturulan ayrılmış nesneye işaret eden bir `shared_ptr` oluşturur ve döndürür.|
|[make_unique](../standard-library/memory-functions.md#make_unique)|Sıfır veya daha fazla bağımsız değişken tarafından oluşturulan ayrılmış nesneye işaret eden bir [unique_ptr](../standard-library/unique-ptr-class.md) oluşturur ve döndürür.|
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|@No__t_0 için tüm olası dönüş değerlerinin numaralandırması.|
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|@No__t_0 Template işlevi kullanılarak ayrılan geçici belleği kaldırır.|
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|@No__t_0 için statik atama.|
|[Kur](../standard-library/memory-functions.md#swap)|İki `shared_ptr` veya `weak_ptr` nesnesi takas edin.|
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.|
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|Belirtilen bellek konumunun ulaşılamaz olduğunu `garbage_collector` bildirir.|
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Nesneleri belirli bir girdi aralığından başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Bir girdi yineleyicisinde belirtilen öğe sayısının bir kopyasını oluşturur. Kopyalar ileri doğru bir yineleyicinin içine yerleştirilir.|
|[uninitialized_default_construct](../standard-library/memory-functions.md#uninitialized_default_construct)|Toplu `uninitialized_default_construct` yöntemi.|
|[uninitialized_default_construct_n](../standard-library/memory-functions.md#uninitialized_default_construct_n)|Toplu `uninitialized_construct` yöntemi.|
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Belirli bir değerin nesnelerini belirli sayıda öğenin başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_move](../standard-library/memory-functions.md#uninitialized_move)|Toplu `uninitialized_move` yöntemi.|
|[uninitialized_move_n](../standard-library/memory-functions.md#uninitialized_move_n)|Toplu `uninitialized_move` yöntemi.|
|[uninitialized_value_construct](../standard-library/memory-functions.md#uninitialized_value_construct)|Toplu `uninitialized_value_construct` yöntemi.|
|[uninitialized_value_construct_n](../standard-library/memory-functions.md#uninitialized_value_construct_n)|Toplu `uninitialized_value_construct` yöntemi.|
|[uses_allocator_v](../standard-library/memory-functions.md#uses_allocator_v)||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/memory-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[işleç = =](../standard-library/memory-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|
|[operator>=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden büyük veya eşit olmasını sınar.|
|[işleç <](../standard-library/memory-operators.md#op_lt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden küçük olmasını sınar.|
|[işleç \< =](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden küçük veya eşit olmasını sınar.|
|[işleç >](../standard-library/memory-operators.md#op_gt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden büyük olmasını sınar.|
|[işleç < <](../standard-library/memory-operators.md#op_lt_lt)|`shared_ptr` Inserter.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[allocator](../standard-library/allocator-class.md)|Sınıf şablonu **, türünde nesne**dizileri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_traits](../standard-library/allocator-traits-class.md)|Ayırıcı tarafından etkinleştirilen kapsayıcı tarafından gerek duyulan bilgilerin tamamını belirleyen nesneyi tanımlar.|
|[auto_ptr](../standard-library/auto-ptr-class.md)|Sınıf şablonu, kapsayan auto_ptr yok edilirken onun işaret ettiği nesnenin silindiğini sağlayan <strong>\*</strong> **türü tür** bir ayrılmış nesneye bir işaretçi depolayan bir nesneyi tanımlar.|
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Bozuk weak_ptr özel durumunu raporlar.|
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|@No__t_0 oluşturulmasına yardımcı olur.|
|[pointer_traits](../standard-library/pointer-traits-struct.md)|@No__t_1 işaretçi türündeki bir ayırıcıyı tanımlayan `allocator_traits` türünde bir nesne için gereken bilgileri sağlar.|
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.|
|[shared_ptr](../standard-library/shared-ptr-class.md)|Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.|
|[unique_ptr](../standard-library/unique-ptr-class.md)|Sahip olunan bir nesnenin işaretçisini depolar. İşaretçi başka bir `unique_ptr` sahip değildir. Sahip yok edildiğinde `unique_ptr` yok edilir.|
|[weak_ptr](../standard-library/weak-ptr-class.md)|Zayıf bağlantılı bir işaretçi sarar.|

### <a name="structures"></a>Yapılar

|||
|-|-|
|[allocator_arg_t](../standard-library/allocator-class.md#allocator_arg_t)||
|[default_delete](../standard-library/default-delete-struct.md)||
|hash|@No__t_0 ve `shared_ptr` için özelleştirilmiş aşırı yüklemeler sağlar.|
|[owner_less](../standard-library/memory-functions.md#owner_less)|Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar.|
|[uses_allocator](../standard-library/allocator-class.md#uses_allocator)||

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[ayırıcı \<void >](../standard-library/allocator-void-class.md)|Yalnızca bu özelleşmiş içerikte anlamlı üye türleri tanımlayarak **void**türüne sahip sınıf şablonu ayırıcı özelleştirmesi.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

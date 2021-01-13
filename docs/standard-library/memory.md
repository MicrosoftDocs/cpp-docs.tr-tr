---
description: 'Daha fazla bilgi edinin: &lt; bellek&gt;'
title: '&lt;bellek&gt;'
ms.date: 08/04/2019
f1_keywords:
- <memory>
helpviewer_keywords:
- memory header
ms.openlocfilehash: 05d5b6e87b23ea2a88e4ff5a8a11c2d6b054691f
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126526"
---
# <a name="ltmemorygt"></a>&lt;bellek&gt;

Bir sınıfı, işleci ve nesneleri ayırmaya ve serbest bırakmaya yardımcı çeşitli şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<memory>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[AddressOf](../standard-library/memory-functions.md#addressof)|Bir nesnenin doğru adresini alır.|
|[acaktır](../standard-library/memory-functions.md#align)|Sağlanan hizalama ve başlangıç adresini temel alarak belirli bir boyut aralığı için bir işaretçi döndürür.|
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Belirtilen bir `shared_ptr` ayırıcıyla verilen tür için ayrılan ve oluşturulan nesneler için bir oluşturur.|
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
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|Const Cast `shared_ptr` .|
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Belirli bir adreste başlayan ve belirtilen blok boyutu içinde kalan karakterlerin izlenebilir işaretçi içermediğini atık toplayıcıya bildirir.|
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.|
|[default_delete](../standard-library/memory-functions.md#default_delete)|İle ayrılmış nesneleri siler `operator new` . İle kullanım için uygundur `unique_ptr` .|
|[destroy_at](../standard-library/memory-functions.md#destroy_at)|Toplu `destroy` Yöntem.|
|[kaldırılır](../standard-library/memory-functions.md#destroy)|Toplu `destroy` Yöntem.|
|[destroy_n](../standard-library/memory-functions.md#destroy_n)|Toplu `destroy` Yöntem.|
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|Dinamik atama `shared_ptr` .|
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|Öğesinden silici alın `shared_ptr` .|
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.|
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Belirli sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.|
|[make_shared](../standard-library/memory-functions.md#make_shared)|`shared_ptr`Varsayılan ayırıcıyı kullanarak sıfır veya daha fazla bağımsız değişken tarafından oluşturulan ayrılmış nesneye işaret eden bir oluşturur ve döndürür.|
|[make_unique](../standard-library/memory-functions.md#make_unique)|Sıfır veya daha fazla bağımsız değişken tarafından oluşturulan ayrılmış nesneye işaret eden bir [unique_ptr](../standard-library/unique-ptr-class.md) oluşturur ve döndürür.|
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|İçin tüm olası dönüş değerlerinin numaralandırması `get_pointer_safety` .|
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|Şablon işlevi kullanılarak ayrılan geçici belleği kaldırır `get_temporary_buffer` .|
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|Statik atama `shared_ptr` .|
|[Kur](../standard-library/memory-functions.md#swap)|İki `shared_ptr` veya nesneyi takas edin `weak_ptr` .|
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.|
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|Belirtilen bir `garbage_collector` bellek konumunun ulaşılamaz olduğunu bildirir.|
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Nesneleri belirli bir girdi aralığından başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Bir girdi yineleyicisinde belirtilen öğe sayısının bir kopyasını oluşturur. Kopyalar ileri doğru bir yineleyicinin içine yerleştirilir.|
|[uninitialized_default_construct](../standard-library/memory-functions.md#uninitialized_default_construct)|Toplu `uninitialized_default_construct` Yöntem.|
|[uninitialized_default_construct_n](../standard-library/memory-functions.md#uninitialized_default_construct_n)|Toplu `uninitialized_construct` Yöntem.|
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Belirli bir değerin nesnelerini belirli sayıda öğenin başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_move](../standard-library/memory-functions.md#uninitialized_move)|Toplu `uninitialized_move` Yöntem.|
|[uninitialized_move_n](../standard-library/memory-functions.md#uninitialized_move_n)|Toplu `uninitialized_move` Yöntem.|
|[uninitialized_value_construct](../standard-library/memory-functions.md#uninitialized_value_construct)|Toplu `uninitialized_value_construct` Yöntem.|
|[uninitialized_value_construct_n](../standard-library/memory-functions.md#uninitialized_value_construct_n)|Toplu `uninitialized_value_construct` Yöntem.|
|[uses_allocator_v](../standard-library/memory-functions.md#uses_allocator_v)||

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç! =](../standard-library/memory-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[işleç = =](../standard-library/memory-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|
|[işleç>=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden büyük veya eşit olmasını sınar.|
|[işleç<](../standard-library/memory-operators.md#op_lt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden küçük olmasını sınar.|
|[işlecinde\<=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden küçük veya eşit olmasını sınar.|
|[işleç>](../standard-library/memory-operators.md#op_gt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden büyük olmasını sınar.|
|[işleç<<](../standard-library/memory-operators.md#op_lt_lt)|`shared_ptr` inserter.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[allocator](../standard-library/allocator-class.md)|Sınıf şablonu **, türünde nesne** dizileri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar.|
|[allocator_traits](../standard-library/allocator-traits-class.md)|Ayırıcı tarafından etkinleştirilen kapsayıcı tarafından gerek duyulan bilgilerin tamamını belirleyen nesneyi tanımlar.|
|[auto_ptr](../standard-library/auto-ptr-class.md)|Sınıf şablonu,  <strong>\*</strong> kapsayan auto_ptr yok edilirken onun işaret ettiği nesnenin silindiğini sağlayan türü tür bir ayrılmış nesneye bir işaretçi depolayan bir nesneyi tanımlar.|
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Bozuk weak_ptr özel durumunu raporlar.|
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|Bir oluşturulmasına yardımcı olur `shared_ptr` .|
|[pointer_traits](../standard-library/pointer-traits-struct.md)|`allocator_traits`İşaretçi türü olan bir ayırıcıyı tanımlayan türünde bir nesne için gereken bilgileri sağlar `Ptr` .|
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.|
|[shared_ptr](../standard-library/shared-ptr-class.md)|Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.|
|[unique_ptr](../standard-library/unique-ptr-class.md)|Sahip olunan bir nesnenin işaretçisini depolar. İşaretçiye ait değildir `unique_ptr` . Sahip yok edildiğinde `unique_ptr` yok edilir.|
|[weak_ptr](../standard-library/weak-ptr-class.md)|Zayıf bağlantılı bir işaretçi sarar.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|-|-|
|[allocator_arg_t](../standard-library/allocator-class.md#allocator_arg_t)||
|[default_delete](../standard-library/default-delete-struct.md)||
|hash|Ve için özelleştirilmiş aşırı yüklemeler sağlar `unique_ptr` `shared_ptr` .|
|[owner_less](../standard-library/memory-functions.md#owner_less)|Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar.|
|[uses_allocator](../standard-library/allocator-class.md#uses_allocator)||

### <a name="specializations"></a>Uzmanlıklar

|Ad|Açıklama|
|-|-|
|[allocator\<void>](../standard-library/allocator-void-class.md)|**`void`** Yalnızca bu özelleşmiş içerikte anlamlı olan üye türlerini tanımlayarak yazmak için sınıf şablonu ayırıcı özelleştirmesi.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

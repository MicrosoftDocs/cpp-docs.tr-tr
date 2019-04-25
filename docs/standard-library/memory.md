---
title: '&lt;Bellek&gt;'
ms.date: 11/04/2016
f1_keywords:
- memory/std::<memory>
- <memory>
- std::<memory>
helpviewer_keywords:
- memory header
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
ms.openlocfilehash: c63421995fdabc94a7e6495df8d9937049dbba9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217345"
---
# <a name="ltmemorygt"></a>&lt;Bellek&gt;

Bir sınıfı, işleci ve nesneleri ayırmaya ve serbest bırakmaya yardımcı çeşitli şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <memory>
```

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[addressof](../standard-library/memory-functions.md#addressof)|Bir nesnenin doğru adresini alır.|
|[align](../standard-library/memory-functions.md#align)|Sağlanan hizalama ve başlangıç adresini temel alarak belirli bir boyut aralığı için bir işaretçi döndürür.|
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Oluşturur bir `shared_ptr` ayrılan ve bir ayırıcıyla verilen tür için oluşturulan nesneler için.|
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|Const dönüştürmesi için `shared_ptr`.|
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Belirli bir adreste başlayan ve belirtilen blok boyutu içinde kalan karakterlerin izlenebilir işaretçi içermediğini atık toplayıcıya bildirir.|
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.|
|[default_delete](../standard-library/memory-functions.md#default_delete)|İle ayrılmış nesneleri siler `operator new`. İle kullanım için uygun `unique_ptr`.|
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|Dynamic_cast `shared_ptr`.|
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|Öğesinden Silici alın `shared_ptr`.|
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.|
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Belirli sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.|
|[make_shared](../standard-library/memory-functions.md#make_shared)|Oluşturur ve döndürür bir `shared_ptr` varsayılan ayırıcı kullanılarak sıfır veya daha fazla bağımsız değişkenden oluşan ayrılmış nesneyi işaret eden.|
|[make_unique](../standard-library/memory-functions.md#make_unique)|Oluşturur ve döndürür bir [unique_ptr](../standard-library/unique-ptr-class.md) sıfır veya daha fazla bağımsız değişkenden oluşan ayrılmış nesneyi işaret eden.|
|[owner_less](../standard-library/memory-functions.md#owner_less)|Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar.|
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|Tüm olası dönüş değerleri numaralandırması `get_pointer_safety`.|
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|Kullanılarak ayrılan geçici bellek ayırmayı iptal eder `get_temporary_buffer` şablon işlevi.|
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|Statik yayın `shared_ptr`.|
|[değiştirme](../standard-library/memory-functions.md#swap)|İki takas `shared_ptr` veya `weak_ptr` nesneleri.|
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.|
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|Bildiren bir `garbage_collector` belirtilen bellek konumuna erişilemiyor.|
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Nesneleri belirli bir girdi aralığından başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Bir girdi yineleyicisinde belirtilen öğe sayısının bir kopyasını oluşturur. Kopyalar ileri doğru bir yineleyicinin içine yerleştirilir.|
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.|
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Belirli bir değerin nesnelerini belirli sayıda öğenin başlatılmamış hedef aralığına kopyalar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/memory-operators.md#op_neq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.|
|[operator==](../standard-library/memory-operators.md#op_eq_eq)|Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.|
|[operator>=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden büyük veya eşit olmasını sınar.|
|[işleç <](../standard-library/memory-operators.md#op_lt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden küçük olmasını sınar.|
|[İşleci\<=](../standard-library/memory-operators.md#op_gt_eq)|Belirtilen sınıfın, bir ayırıcı nesnesinin ikinci bir ayırıcı nesnesinin değerinden küçük veya eşit olmasını sınar.|
|[operator >](../standard-library/memory-operators.md#op_gt)|Belirtilen sınıfın bir nesnesinin ikinci bir nesnesinin değerinden büyük olmasını sınar.|
|[işleç <<](../standard-library/memory-operators.md#op_lt_lt)|`shared_ptr` inserter.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[allocator](../standard-library/allocator-class.md)|Şablon sınıfı türünde nesne dizileri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlayan **türü**.|
|[allocator_traits](../standard-library/allocator-traits-class.md)|Ayırıcı tarafından etkinleştirilen kapsayıcı tarafından gerek duyulan bilgilerin tamamını belirleyen nesneyi tanımlar.|
|[auto_ptr](../standard-library/auto-ptr-class.md)|Şablon sınıfı türünün ayrılmış bir nesneye yönelik bir işaretçi depolayan nesneyi tanımlar **türü** <strong>\*</strong> nesne için hangi BT silindiğinde işaret ettiği, kapsayan auto_ptr alır sağlar yok.|
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Bozuk weak_ptr özel durumunu raporlar.|
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|Üretmeye yardımcı olur bir `shared_ptr`.|
|[pointer_traits](../standard-library/pointer-traits-struct.md)|Şablon sınıfın bir nesnesinin gerektirdiği bilgileri sağlar `allocator_traits` bir ayırıcı işaretçi türü ile açıklamak için `Ptr`.|
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.|
|[shared_ptr](../standard-library/shared-ptr-class.md)|Dinamik olarak tahsis edilen bir nesnenin çevresine bir başvuru sayılan akıllı işaretçi sarar.|
|[unique_ptr](../standard-library/unique-ptr-class.md)|Sahip olunan bir nesnenin işaretçisini depolar. Başka hiçbir işaretçinin sahibi değildir `unique_ptr`. `unique_ptr` Sahibi kaldırıldığında yok.|
|[weak_ptr](../standard-library/weak-ptr-class.md)|Zayıf bağlantılı bir işaretçi sarar.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[Allocator\<void >](../standard-library/allocator-void-class.md)|Yalnızca bu özelleştirilen içerikte anlamlı üye türleri tanımlayarak void türüne şablon sınıf ayırıcı uzmanlığı.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

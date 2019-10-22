---
title: '&lt;atomic&gt;'
ms.date: 11/04/2016
f1_keywords:
- <atomic>
- atomic/std::atomic_int_least32_t
- atomic/std::atomic_ullong
- atomic/std::atomic_ptrdiff_t
- atomic/std::atomic_char16_t
- atomic/std::atomic_schar
- atomic/std::atomic_ulong
- atomic/std::atomic_uint_fast32_t
- atomic/std::atomic_uint8_t
- atomic/std::atomic_int32_t
- atomic/std::atomic_uint_fast64_t
- atomic/std::atomic_uint32_t
- atomic/std::atomic_int16_t
- atomic/std::atomic_uintmax_t
- atomic/std::atomic_intmax_t
- atomic/std::atomic_long
- atomic/std::atomic_int
- atomic/std::atomic_uint_least8_t
- atomic/std::atomic_size_t
- atomic/std::atomic_uint_fast16_t
- atomic/std::atomic_wchar_t
- atomic/std::atomic_int_fast64_t
- atomic/std::atomic_uint_fast8_t
- atomic/std::atomic_int_fast8_t
- atomic/std::atomic_intptr_t
- atomic/std::atomic_uint
- atomic/std::atomic_uint16_t
- atomic/std::atomic_char32_t
- atomic/std::atomic_uint64_t
- atomic/std::atomic_ushort
- atomic/std::atomic_int_least16_t
- atomic/std::atomic_char
- atomic/std::atomic_uint_least32_t
- atomic/std::atomic_uintptr_t
- atomic/std::atomic_short
- atomic/std::atomic_llong
- atomic/std::atomic_uint_least16_t
- atomic/std::atomic_int_fast16_t
- atomic/std::atomic_int_least8_t
- atomic/std::atomic_int_least64_t
- atomic/std::atomic_int_fast32_t
- atomic/std::atomic_uchar
- atomic/std::atomic_int8_t
- atomic/std::atomic_int64_t
- atomic/std::atomic_uint_least64_t
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
ms.openlocfilehash: b33ec1e7fdc7f93062248a9ad42c78c3b30801fe
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688458"
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

Atomik işlemleri destekleyen türler oluşturmak için kullanılacak sınıfları ve sınıf şablonlarını tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <atomic>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

Atomik bir işlemin, bir nesneyi, karşılıklı dışlama kilitleri kullanmadan doğru şekilde işlemek için birden çok iş parçacığı kullanmanıza yardımcı olan iki temel özelliği vardır.

- Atomik bir işlem, farklı bir iş parçacığından aynı nesne üzerinde bulunan ikinci atomik bir işlem, nesnenin durumunu yalnızca ilk atomik işlemden önce veya sonra alabilir.

- Atomik bir işlem, [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenine göre, aynı iş parçacığında diğer atomik işlemlerin etkilerinin görünürlüğü için sıralama gereksinimlerini belirler. Sonuç olarak, sıralama gereksinimlerini ihlal eden derleyici iyileştirmelerini engeller.

Bazı platformlarda, `mutex` kilitleri kullanmadan bazı türler için atomik işlemleri verimli bir şekilde uygulamak mümkün olmayabilir. Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa *kilit ücretsizdir* .

**C++ 11**: sinyal işleyicilerinde, `obj.is_lock_free()` veya `atomic_is_lock_free(x)` true ise bir nesne `obj` Atomik işlemler gerçekleştirebilirsiniz.

[Atomic_flag](../standard-library/atomic-flag-structure.md) sınıfı, **bool** bayrağını tutan en düşük atomik bir tür sağlar. İşlemleri her zaman kilitsiz değildir.

Sınıf şablonu `atomic<T>` bağımsız değişken türü `T` bir nesneyi depolar ve bu depolanan değere atomik erişim sağlar. [Memckopyala](../c-runtime-library/reference/memcpy-wmemcpy.md) kullanılarak kopyalanabilen ve [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)kullanarak eşitlik için test edilmiş herhangi bir tür kullanarak bu örneği oluşturabilirsiniz. Özellikle, bu gereksinimleri karşılayan Kullanıcı tanımlı türlerle ve birçok durumda kayan nokta türleriyle kullanabilirsiniz.

Şablonda Ayrıca, tamsayı türleri için bir uzmanlık kümesi ve işaretçiler için kısmi özelleşmeler vardır. Bu uzmanlıklar, birincil şablon aracılığıyla kullanılamayan ek işlemler sağlar.

## <a name="pointer-specializations"></a>İşaretçi özelleştirilmiş oluşturmaları

@No__t_0 kısmi uzmanlık tüm işaretçi türleri için geçerlidir. İşaretçi aritmetik için yöntemler sağlar.

## <a name="integral-specializations"></a>Integral Specialmeler

@No__t_0 uzmanlık tüm integral türleri için geçerlidir. Bunlar, birincil şablon aracılığıyla kullanılamayan ek işlemler sağlar.

Her `atomic<integral>` türü, bu türdeki işlemlerin kilitleme dışı olup olmadığını derleme zamanında belirleyebilmek için bir `if directive` kullanabileceğiniz bir makroya sahiptir. Makronun değeri sıfırsa, türdeki işlemler kilitleme ücretsizdir. Değer 1 ise, işlemler kilit boş olabilir ve bir çalışma zamanı denetimi gereklidir. Değer 2 ise, işlemler kilitleme ücretsizdir. ' @No__t_0 işlevini kullanarak, türdeki işlemlerin kilitleme dışı olup olmadığı çalışma zamanını belirleyebilirsiniz.

İntegral türlerinin her biri için, söz konusu integral türünün bir nesnesini yöneten karşılık gelen bir adlandırılmış atomik tür vardır. Her `atomic_integral` türü, karşılık gelen `atomic<T>` örneklemeyle aynı üye işlevleri kümesine sahiptir ve üye olmayan atomik işlevlerden herhangi birine geçirilebilir.

|`atomic_integral` türü|Integral türü|`atomic_is_lock_free` makro|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|**char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_schar`|**işaretli karakter**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_uchar`|**işaretsiz karakter**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_char16_t`|`char16_t`|ATOMIC_CHAR16_T_LOCK_FREE|
|`atomic_char32_t`|`char32_t`|ATOMIC_CHAR32_T_LOCK_FREE|
|`atomic_wchar_t`|**wchar_t**|ATOMIC_WCHAR_T_LOCK_FREE|
|`atomic_short`|**short**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_ushort`|**işaretsiz kısa**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_int`|**int**|ATOMIC_INT_LOCK_FREE|
|`atomic_uint`|**işaretsiz int**|ATOMIC_INT_LOCK_FREE|
|`atomic_long`|**long**|ATOMIC_LONG_LOCK_FREE|
|`atomic_ulong`|**imzasız Long**|ATOMIC_LONG_LOCK_FREE|
|`atomic_llong`|**uzun uzun**|ATOMIC_LLONG_LOCK_FREE|
|`atomic_ullong`|**imzasız uzun uzun**|ATOMIC_LLONG_LOCK_FREE|

@No__t_0inttypes. h > üst bilgisinde tanımlanan bazı türlerin atomik şablonunun uzmanlıkları için typedef adları mevcuttur.

|Atomik tür|TypeDef adı|
|-----------------|------------------|
|`atomic_int8_t`|`atomic<int8_t>`|
|`atomic_uint8_t`|`atomic<uint8_t>`|
|`atomic_int16_t`|`atomic<int16_t>`|
|`atomic_uint16_t`|`atomic<uint16_t>`|
|`atomic_int32_t`|`atomic<int32_t>`|
|`atomic_uint32_t`|`atomic<uint32_t>`|
|`atomic_int64_t`|`atomic<int64_t>`|
|`atomic_uint64_t`|`atomic<uint64_t>`|
|`atomic_int_least8_t`|`atomic<int_least8_t>`|
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|
|`atomic_int_least16_t`|`atomic<int_least16_t>`|
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|
|`atomic_int_least32_t`|`atomic<int_least32_t>`|
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|
|`atomic_int_least64_t`|`atomic<int_least64_t>`|
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|
|`atomic_intptr_t`|`atomic<intptr_t>`|
|`atomic_uintptr_t`|`atomic<uintptr_t>`|
|`atomic_size_t`|`atomic<size_t>`|
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|
|`atomic_intmax_t`|`atomic<intmax_t>`|
|`atomic_uintmax_t`|`atomic<uintmax_t>`|

## <a name="structs"></a>Yapılar

|Name|Açıklama|
|----------|-----------------|
|[atomic Yapısı](../standard-library/atomic-structure.md)|Depolanan bir değerde Atomik işlemler gerçekleştiren bir nesneyi açıklar.|
|[atomic_flag Yapısı](../standard-library/atomic-flag-structure.md)|Bir **bool** bayrağını sıradan olarak ayarlayan ve temizleyen bir nesneyi tanımlar.|

## <a name="enums"></a>Numaralandırmalar

|Name|Açıklama|
|----------|-----------------|
|[memory_order numaralandırması](../standard-library/atomic-enums.md#memory_order_enum)|Bellek konumlarında eşitleme işlemleri için simgesel adlar sağlar. Bu işlemler, bir iş parçacığındaki atamaların diğerinden nasıl görünür hale geldiğini etkiler.|

## <a name="functions"></a>İşlevler

Aşağıdaki listede `_explicit` olmayan işlevler, `memory_order_seq_cst` örtük [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenlerine sahip olmaları dışında, karşılık gelen `_explicit` semantiklerine sahiptir.

|Name|Açıklama|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|*Atomik karşılaştırma ve değişim* işlemi gerçekleştirir.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|*Atomik karşılaştırma ve değişim* işlemi gerçekleştirir.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|*Zayıf atomik karşılaştırma ve değişim* işlemi gerçekleştirir.|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|*Zayıf atomik karşılaştırma ve değişim* işlemi gerçekleştirir.|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|Saklı bir değeri değiştirir.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|Saklı bir değeri değiştirir.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|Varolan bir saklı değere belirtilen bir değer ekler.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|Varolan bir saklı değere belirtilen bir değer ekler.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|Belirtilen değerde ve varolan bir depolanmış değerde bit düzeyinde `and` gerçekleştirir.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|Belirtilen değerde ve varolan bir depolanmış değerde bit düzeyinde `and` gerçekleştirir.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|Belirtilen değerde ve varolan bir depolanmış değerde bit düzeyinde `or` gerçekleştirir.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|Belirtilen değerde ve varolan bir depolanmış değerde bit düzeyinde `or` gerçekleştirir.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|Varolan bir depolanmış değerden belirtilen değeri çıkartır.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|Varolan bir depolanmış değerden belirtilen değeri çıkartır.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|Belirtilen değerde ve varolan bir depolanmış değerde bit düzeyinde `exclusive or` gerçekleştirir.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|Belirtilen değerde ve varolan bir depolanmış değerde bit düzeyinde `exclusive or` gerçekleştirir.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|Bir `atomic_flag` nesnesindeki bayrağı **false**olarak ayarlar.|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|Bir `atomic_flag` nesnesindeki bayrağı **false**olarak ayarlar.|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|Bir `atomic_flag` nesnesindeki bayrağı **true**olarak ayarlar.|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|Bir `atomic_flag` nesnesindeki bayrağı **true**olarak ayarlar.|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|@No__t_0 nesnesindeki depolanan değeri ayarlar.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|Belirtilen bir nesne üzerindeki atomik işlemlerin kilitli olup olmadığını belirtir.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|Sıradan olarak bir değer alır.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|Sıradan olarak bir değer alır.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|Aynı iş parçacığında çalıştırılan sinyal işleyicilerine sahip bir çağıran iş parçacığı arasında bellek sıralama gereksinimleri kuran bir *çit* görevi görür.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|Bir değeri atomicbir şekilde depolar.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|Bir değeri atomicbir şekilde depolar.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|, Diğer balıklara göre bellek sıralama gereksinimlerini belirleyen bir *çit* görevi görür.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|Olası bir bağımlılık zincirini keser.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

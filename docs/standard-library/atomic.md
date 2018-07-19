---
title: '&lt;atomik&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54ea69a53204de2d304340ed042b3ba028dd404c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966647"
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

Atomik işlemleri destekleyen türler oluşturmak için kullanılacak şablon sınıfları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <atomic>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Derlenmiş kodda **/CLR**, bu başlığı engellenir.

Atomik işlem iki içeren yardımcı olan anahtar özelliklerini mutex kilitleri kullanmadan bir nesne doğru bir şekilde işlemek için birden çok iş parçacığı kullanın.

- Bölünemez atomik bir işlem olduğundan, farklı bir iş parçacığından aynı nesne üzerinde ikinci bir atomik işlem yalnızca önce veya sonra ilk atomik işlem nesnenin durumu elde edebilirsiniz.

- Temel kendi [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni, atomik bir işlem oluşturur aynı iş parçacığında diğer atomik işlemler etkilerini görünürlük gereksinimleri sıralama. Sonuç olarak, sıralama gereksinimlerini ihlal derleyici iyileştirmeleri engeller.

Bazı platformlarda, bunu kullanmadan bazı türleri atomik işlemlerin verimli bir şekilde uygulanması mümkün olmayabilir `mutex` kilitler. Atomik tür *kilitsizdir* hiçbir bu türdeki atomik işlemler kilit kullanmıyorsa.

**C ++ 11**: sinyal işleyiciler içinde bir nesne üzerinde yapılan atomik işlemlerin gerçekleştirebileceğiniz `obj` varsa `obj.is_lock_free()` veya `atomic_is_lock_free(x)` doğrudur.

Sınıf [atomic_flag](../standard-library/atomic-flag-structure.md) tutar en az bir atomik türü sağlayan bir **bool** bayrağı. Kendi işlemlerdir her zaman kilitsizdir.

Şablon sınıfı `atomic<T>` kendi bağımsız değişken türünde bir nesne depolar `T` ve o depolanan değeri atomik erişim sağlar. Kullanılarak kopyalanmasını herhangi bir türü kullanarak oluşturabileceğiniz [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) ve kullanarak eşitlik için test [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md). Özellikle, bu gereksinimleri karşılayan, kullanıcı tanımlı türler ve çoğu durumda, kayan nokta türleri ile kullanabilirsiniz.

Şablon uzmanlıkları tam sayı türleri için işaretçiler için kısmi özelleştirmede ve ayrıca bir ayarlanmış. Bu uzmanlıklar, birincil şablonu aracılığıyla kullanılabilir olmayan ek işlemleri sağlar.

## <a name="pointer-specializations"></a>İşaretçi uzmanlıklar

`atomic<T *>` Kısmi uzmanlıklar, tüm işaretçi türleri için geçerlidir. Bunlar, işaretçi aritmetik için yöntemleri sağlar.

## <a name="integral-specializations"></a>Uzmanlıkları

`atomic<integral>` Uzmanlıkları tüm integral türleri için geçerlidir. Bunlar birincil şablonu aracılığıyla kullanılabilir olmayan ek işlemler sağlar.

Her `atomic<integral>` türünde kullanabileceğiniz karşılık gelen bir makro bir `if directive` derleme zamanında bu tür işlemler olup olmadığını belirlemek için kilitsizdir. Makrosunun değeri sıfır ise, türü üzerinde işlemler olmayan kilitsizdir. Değer 1 ise, işlemler kilidi serbest bırakın ve bir çalışma zamanı olabilir onay gereklidir. Değer 2 ise işlemlerdir kilitsizdir. İşlev kullanabilir `atomic_is_lock_free` çalışma zamanında işlem türü olup olmadığını belirlemek için kilitsizdir.

Her tamsayı türleri için bu integral türünde bir nesne yöneten karşılık gelen adlandırılmış atomik türü yoktur. Her `atomic_integral` türüne sahip karşılık gelen örneğinin aynı kümesi üye işlevleri `atomic<T>` ve tüm üye olmayan atomik işlevlerini geçirilebilir.

|`atomic_integral` Türü|Tamsayı türü|`atomic_is_lock_free` Makrosu|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|**char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_schar`|**İmzalı char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_uchar`|**İmzasız char**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_char16_t`|`char16_t`|ATOMIC_CHAR16_T_LOCK_FREE|
|`atomic_char32_t`|`char32_t`|ATOMIC_CHAR32_T_LOCK_FREE|
|`atomic_wchar_t`|**wchar_t**|ATOMIC_WCHAR_T_LOCK_FREE|
|`atomic_short`|**short**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_ushort`|**İmzasız short**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_int`|**int**|ATOMIC_INT_LOCK_FREE|
|`atomic_uint`|**işaretsiz int**|ATOMIC_INT_LOCK_FREE|
|`atomic_long`|**long**|ATOMIC_LONG_LOCK_FREE|
|`atomic_ulong`|**İmzasız long**|ATOMIC_LONG_LOCK_FREE|
|`atomic_llong`|**Long long**|ATOMIC_LLONG_LOCK_FREE|
|`atomic_ullong`|**İmzasız uzun uzun**|ATOMIC_LLONG_LOCK_FREE|

TypeDef adları mevcut atomik şablon uzmanlıkları için bazı üst bilgisinde tanımlanan türleri için \<inttypes.h >.

|Atomik türü|TypeDef adı|
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

|Ad|Açıklama|
|----------|-----------------|
|[atomic Yapısı](../standard-library/atomic-structure.md)|Depolanan değeri atomik işlemleri gerçekleştiren bir nesneyi tanımlar.|
|[atomic_flag Yapısı](../standard-library/atomic-flag-structure.md)|Atomik olarak ayarlayan ve temizleyen bir nesneyi tanımlayan bir **bool** bayrağı.|

## <a name="enums"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[memory_order sabit listesi](../standard-library/atomic-enums.md#memory_order_enum)|Bellek konumlarında eşitleme işlemleri için simgesel adlar sağlar. Bu işlemlerin nasıl atamaları bir iş parçacığındaki başka bir atamada görülür hale etkiler.|

## <a name="functions"></a>İşlevler

Aşağıdaki listede, içinde son işlevlerin `_explicit` karşılık gelen semantiklere sahip `_explicit`örtük sahip oldukları dışında [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenleri `memory_order_seq_cst`.

|Ad|Açıklama|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|Gerçekleştiren bir *atomik karşılaştırma ve değişim* işlemi.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|Gerçekleştiren bir *atomik karşılaştırma ve değişim* işlemi.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|Gerçekleştiren bir *zayıf atomik karşılaştırma ve exchange* işlemi.|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|Gerçekleştiren bir *zayıf atomik karşılaştırma ve exchange* işlemi.|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|Depolanmış bir değerin yerini alır.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|Depolanmış bir değerin yerini alır.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|Belirtilen bir değeri depolanan mevcut bir değeri ekler.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|Belirtilen bir değeri depolanan mevcut bir değeri ekler.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|Bit düzeyinde gerçekleştirir `and` belirtilen bir değer ve depolanan varolan değeri.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|Bit düzeyinde gerçekleştirir `and` belirtilen bir değer ve depolanan varolan değeri.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|Bit düzeyinde gerçekleştirir `or` belirtilen bir değer ve depolanan varolan değeri.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|Bit düzeyinde gerçekleştirir `or` belirtilen bir değer ve depolanan varolan değeri.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|Belirtilen bir değeri depolanan mevcut bir değeri çıkarır.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|Belirtilen bir değeri depolanan mevcut bir değeri çıkarır.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|Bit düzeyinde gerçekleştirir `exclusive or` belirtilen bir değer ve depolanan varolan değeri.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|Bit düzeyinde gerçekleştirir `exclusive or` belirtilen bir değer ve depolanan varolan değeri.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|Bayrağı ayarlar bir `atomic_flag` nesnesini **false**.|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|Bayrağı ayarlar bir `atomic_flag` nesnesini **false**.|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|Bayrağı ayarlar bir `atomic_flag` nesnesini **true**.|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|Bayrağı ayarlar bir `atomic_flag` nesnesini **true**.|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|Depolanan değeri ayarlar bir `atomic` nesne.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|Belirtilen bir nesne üzerinde yapılan atomik işlemlerin olup olmadığını belirten kilitsizdir.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|Atomik olarak bir değer alır.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|Atomik olarak bir değer alır.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|Görevi gören bir *dilimi* bellek gereksinimleri bir arama içinde sınırlar arasında iş parçacığı sıralaması olan aynı iş parçacığında çalıştırılan sinyal işleyicileri oluşturur.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|Bir değeri atomik olarak depolar.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|Bir değeri atomik olarak depolar.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|Görevi gören bir *dilimi* bellek sıralaması parçacığındaki diğer çitler gereksinimlerini oluşturur.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|Olası bir bağımlılık zinciri keser.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>

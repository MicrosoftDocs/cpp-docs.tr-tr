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
ms.openlocfilehash: 74dc0fde7ea066707bb6e93592420009b882ee21
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

Atomik işlemleri destekleyen türler oluşturmak için kullanılacak şablonu sınıfları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <atomic>
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Kullanarak derlenmiş kod **/CLR**, bu başlığı engellenir.

İki atomik bir işlem var yardımcı anahtar özelliklerini mutex kilitleri kullanmadan bir nesne doğru şekilde işlemek için birden çok iş parçacığı kullanın.

- Atomik bir işlem bölünemez olduğundan, ikinci bir atomik işlem aynı nesne farklı bir iş üzerinde yalnızca önce veya sonra ilk atomik işlemi nesnenin durumunu elde edebilirsiniz.

- Temel kendi [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni, atomik bir işlem kurar diğer atomik işlemleri etkilerini görünürlük gereksinimleri aynı iş parçacığında sıralama. Sonuç olarak, sipariş gereksinimleri ihlal derleyici iyileştirmelerini engeller.

Bazı platformlarda, kullanmadan atomik işlemleri bazı türleri için verimli bir şekilde uygulanmasını mümkün olmayabilir `mutex` kilitler. Atomik bir tür olduğundan *kilidi serbest* ilgili türdeki atomik bir işlem kilitleri kullanıyorsanız.

**C ++ 11**: sinyal-işleyicileri bir nesne üzerinde atomik işlemler gerçekleştirebilirsiniz `obj` varsa `obj.is_lock_free()` veya `atomic_is_lock_free(x)` doğrudur.

Sınıf [atomic_flag](../standard-library/atomic-flag-structure.md) sağlayan tutan en az bir atomik türü bir `bool` bayrağı. Yaptığı işlemler her zaman olan kilidi serbest.

Şablon sınıfı `atomic<T>` kendi bağımsız değişkeni türünde bir nesne depolar `T` ve bu depolanmış değeri atomik erişim sağlar. Bunu kullanarak kopyaladığınız herhangi bir türü kullanarak örneği [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) ve kullanılarak eşitlik için test [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md). Özellikle, bu gereksinimleri karşılayan kullanıcı tanımlı türler ile ve çoğu durumda, kayan nokta türleri ile kullanabilirsiniz.

Şablonu, bir dizi tam sayı türleri için özelleştirmeleri ve işaretçiler için kısmi özelleştirmesi da sahiptir. Bu özelleştirmeleri birincil şablonu aracılığıyla kullanılabilir olmayan ek işlemler sağlar.

## <a name="pointer-specializations"></a>İşaretçi özelleştirmeleri

`atomic<T *>` Kısmi özelleştirmeleri tüm işaretçi türleri için geçerlidir. İşaretçi aritmetiği yöntemlerini sağlarlar.

## <a name="integral-specializations"></a>Tam sayı özelleştirmeleri

`atomic<integral>` Özelleştirmeleri tüm tam sayı türleri için geçerlidir. Birincil şablonu aracılığıyla kullanılabilir olmayan ek işlemleri sağlarlar.

Her `atomic<integral>` türünde kullanabileceğiniz karşılık gelen bir makrosu bir `if directive` derleme zamanında işlemleri ilgili türdeki olup olmadığını belirlemek için kilidi serbest. Makro değeri sıfır ise, işlemleri türünde olmayan kilidi serbest. Değer 1 ise, işlemleri kilidi serbest ve bir çalışma zamanı olabilir onay gereklidir. Değer 2 ise işlemleridir kilidi serbest. İşlev kullanabilirsiniz `atomic_is_lock_free` çalışma zamanında tür işlemler olup olmadığını belirlemek için kilidi serbest.

Her tam sayı türleri için bu Tamsayı türünde bir nesne yöneten karşılık gelen bir adlandırılmış atomik türü yok. Her `atomic_integral` türü karşılık gelen örnek oluşturma aynı sayıda üye işlevi `atomic<T>` ve herhangi bir üye olmayan atomik işlevleri için geçirilebilir.

|`atomic_integral` Türü|Tam sayı türü|`atomic_is_lock_free` Makrosu|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|`char`|`ATOMIC_CHAR_LOCK_FREE`|
|`atomic_schar`|`signed char`|`ATOMIC_CHAR_LOCK_FREE`|
|`atomic_uchar`|`unsigned char`|`ATOMIC_CHAR_LOCK_FREE`|
|`atomic_char16_t`|`char16_t`|`ATOMIC_CHAR16_T_LOCK_FREE`|
|`atomic_char32_t`|`char32_t`|`ATOMIC_CHAR32_T_LOCK_FREE`|
|`atomic_wchar_t`|`wchar_t`|`ATOMIC_WCHAR_T_LOCK_FREE`|
|`atomic_short`|`short`|`ATOMIC_SHORT_LOCK_FREE`|
|`atomic_ushort`|`unsigned short`|`ATOMIC_SHORT_LOCK_FREE`|
|`atomic_int`|`int`|`ATOMIC_INT_LOCK_FREE`|
|`atomic_uint`|`unsigned int`|`ATOMIC_INT_LOCK_FREE`|
|`atomic_long`|`long`|`ATOMIC_LONG_LOCK_FREE`|
|`atomic_ulong`|`unsigned long`|`ATOMIC_LONG_LOCK_FREE`|
|`atomic_llong`|`long long`|`ATOMIC_LLONG_LOCK_FREE`|
|`atomic_ullong`|`unsigned long long`|`ATOMIC_LLONG_LOCK_FREE`|

TypeDef adları mevcut atomik şablon özelleştirmeleri üstbilgisinde tanımlanan türlerden bazıları için için \<inttypes.h >.

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
|[atomic Yapısı](../standard-library/atomic-structure.md)|Depolanan değer atomik işlemleri gerçekleştiren bir nesne açıklar.|
|[atomic_flag Yapısı](../standard-library/atomic-flag-structure.md)|Otomatik olarak ayarlar ve temizler bir nesneyi tanımlayan bir `bool` bayrağı.|

## <a name="enums"></a>Numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[memory_order Enum](../standard-library/atomic-enums.md#memory_order_enum)|Bellek konumlarını eşitleme işlemleri için simgesel adları sağlar. Bu işlemlerin nasıl bir iş parçacığı atamalarını başka bir programda görünür hale gelmiştir etkiler.|

## <a name="functions"></a>İşlevler

Aşağıdaki listede, içinde bitmeyen işlevleri `_explicit` ilgili semantiklerine sahip `_explicit`örtük sahip olmaları dışında [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız `memory_order_seq_cst`.

|Ad|Açıklama|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|Gerçekleştiren bir *atomik Karşılaştır ve exchange* işlemi.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|Gerçekleştiren bir *atomik Karşılaştır ve exchange* işlemi.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|Gerçekleştiren bir *zayıf atomik karşılaştırın ve exchange* işlemi.|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|Gerçekleştiren bir *zayıf atomik karşılaştırın ve exchange* işlemi.|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|Depolanmış bir değerin yerini alır.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|Depolanmış bir değerin yerini alır.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|Belirtilen değer var olan bir saklı değerine ekler.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|Belirtilen değer var olan bir saklı değerine ekler.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|Bit tabanlı gerçekleştirir `and` belirtilen değere ve bir depolanan mevcut değeri.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|Bit tabanlı gerçekleştirir `and` belirtilen değere ve bir depolanan mevcut değeri.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|Bit tabanlı gerçekleştirir `or` belirtilen değere ve bir depolanan mevcut değeri.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|Bit tabanlı gerçekleştirir `or` belirtilen değere ve bir depolanan mevcut değeri.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|Varolan bir depolanmış değeri belirtilen değeri çıkarır.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|Varolan bir depolanmış değeri belirtilen değeri çıkarır.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|Bit tabanlı gerçekleştirir `exclusive or` belirtilen değere ve bir depolanan mevcut değeri.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|Bit tabanlı gerçekleştirir `exclusive or` belirtilen değere ve bir depolanan mevcut değeri.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|Bayrak ayarlar bir `atomic_flag` nesnesine `false`.|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|Bayrak ayarlar bir `atomic_flag` nesnesine `false`.|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|Bayrak ayarlar bir `atomic_flag` nesnesine `true`.|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|Bayrak ayarlar bir `atomic_flag` nesnesine `true`.|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|Saklanan değeri ayarlar bir `atomic` nesnesi.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|Belirtilen bir nesne üzerinde atomik işlemleri olup olmadığını belirtir kilidi serbest.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|Otomatik olarak bir değer alır.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|Otomatik olarak bir değer alır.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|Görevi gören bir *dilimi* gereksinimleri bir arama dilimleri arasında iş parçacığı sıralama belleğe sahip iş parçacığında yürütülen sinyal işleyicileri oluşturur.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|Otomatik olarak bir değerini depolar.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|Otomatik olarak bir değerini depolar.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|Görevi gören bir *dilimi* bellek gereksinimleri diğer dilimleri göre sıralama oluşturur.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|Olası bağımlılık zinciri keser.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>

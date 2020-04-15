---
title: 3. Çalışma zamanı kitaplık işlevleri
ms.date: 05/13/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 767c006b0a2d81af4d1f8f2e23f84d7847326f31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370281"
---
# <a name="3-run-time-library-functions"></a>3. Çalışma zamanı kitaplığı işlevleri

Bu bölümde OpenMP C ve C++ çalışma zamanı kitaplığı işlevleri açıklanmaktadır. Başlık ** \<omp.h>** iki tür bildirir, paralel yürütme ortamını denetlemek ve sorgulamak için kullanılabilecek çeşitli işlevler, ve verilere erişimi eşitlemek için kullanılabilecek işlevleri kilitleyin.

Tür, `omp_lock_t` bir kilidin kullanılabilir olduğunu veya bir iş parçacığının bir kilidi nolduğunu ifade edebilen bir nesne türüdür. Bu kilitler *basit kilitler*olarak adlandırılır.

Tür, `omp_nest_lock_t` kilidin kullanılabilir olduğunu veya kilidin ve *iç içe geçme sayısının* sahibi olan iş parçacığının kimliğini (aşağıda açıklanmıştır) temsil edebilen bir nesne türüdür. Bu kilitler *nestable kilitler*olarak adlandırılır.

Kitaplık işlevleri "C" bağlantısı na sahip dış işlevlerdir.

Bu bölümdeki açıklamalar aşağıdaki konulara ayrılmıştır:

- [Yürütme ortamı işlevleri](#31-execution-environment-functions)
- [Kilit fonksiyonları](#32-lock-functions)
- [Zamanlama rutinleri](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3.1 Yürütme ortamı fonksiyonları

Bu bölümde açıklanan işlevler iş parçacıklarını, işlemcileri ve paralel ortamı etkiler ve izler:

- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_get_max_threads](#313-omp_get_max_threads-function)
- [omp_get_thread_num](#314-omp_get_thread_num-function)
- [omp_get_num_procs](#315-omp_get_num_procs-function)
- [omp_in_parallel](#316-omp_in_parallel-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [omp_get_dynamic](#318-omp_get_dynamic-function)
- [omp_set_nested](#319-omp_set_nested-function)
- [omp_get_nested](#3110-omp_get_nested-function)

### <a name="311-omp_set_num_threads-function"></a><a name="311-omp_set_num_threads-function"></a>3.1.1 omp_set_num_threads fonksiyonu

İşlev, `omp_set_num_threads` bir `num_threads` yan tümce belirtmeden sonraki paralel bölgeler için kullanılacak varsayılan iş parçacığı sayısını ayarlar. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

*parametre num_threads* değeri pozitif bir tamsayı olmalıdır. Etkisi, iş parçacığı sayısının dinamik olarak ayarlanıp etkinleştirilemeyeceğine bağlıdır. `omp_set_num_threads` İş parçacığı işlevi ve dinamik ayarlama arasındaki etkileşim hakkında kapsamlı bir kural kümesi için [bölüm 2.3'e](2-directives.md#23-parallel-construct)bakın.

Bu işlev, `omp_in_parallel` işlevin sıfır döndürdüğü programın bir bölümünden çağrıldığında yukarıda açıklanan etkilere sahiptir. `omp_in_parallel` İşlevin sıfır olmayan bir değeri döndürdüğü programın bir bölümünden çağrılırsa, bu işlevin davranışı tanımsız dır.

Bu çağrının ortam `OMP_NUM_THREADS` değişkeninden önceliği vardır. Çağrılar `omp_set_num_threads` veya `OMP_NUM_THREADS` ortam değişkeni ayarlayarak kurulabilen iş parçacığı sayısı için varsayılan değer, `parallel` `num_threads` yan tümcebelirterek tek bir yönergede açıkça geçersiz kılınabilir.

Daha fazla bilgi için [omp_set_dynamic.](#317-omp_set_dynamic-function)

#### <a name="cross-references"></a>Çapraz referans

- [omp_set_dynamic](#317-omp_set_dynamic-function) fonksiyonu
- [omp_get_dynamic](#318-omp_get_dynamic-function) fonksiyonu
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) ortam değişkeni
- [num_threads](2-directives.md#23-parallel-construct) maddesi

### <a name="312-omp_get_num_threads-function"></a><a name="312-omp_get_num_threads-function"></a>3.1.2 omp_get_num_threads fonksiyonu

İşlev, `omp_get_num_threads` çağrıldığı paralel bölgeyi yürüten takımdaki şu anda bulunan iş parçacığı sayısını döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

Yan `num_threads` tümce, `omp_set_num_threads` işlev `OMP_NUM_THREADS` ve ortam değişkeni takımdaki iş parçacığı sayısını denetler.

İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmamışsa, varsayılan değer uygulama tanımlıdır. Bu işlev en yakın çevreleyen `parallel` yönergeye bağlanır. Bir programın seri bölümünden veya seri olarak iç içe geçen bir paralel bölgeden çağrılırsa, bu işlev 1 döndürür.

Daha fazla bilgi için [omp_set_dynamic.](#317-omp_set_dynamic-function)

#### <a name="cross-references"></a>Çapraz referans

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [parallel](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a><a name="313-omp_get_max_threads-function"></a>3.1.3 omp_get_max_threads fonksiyonu

İşlev, `omp_get_max_threads` kodun bu noktasında bir yan tümcesi olmayan paralel bir bölge görülse, takım oluşturmak için `num_threads` kullanılacak iş parçacığı sayısı kadar olduğu garanti edilen bir tamsayı döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

Aşağıdaki değeri üzerinde bir alt sınır `omp_get_max_threads`ifade eder:

> *iş parçacıkları için kullanılan-sonraki takım için* <= `omp_get_max_threads`

Başka bir paralel bölge `num_threads` belirli sayıda iş parçacığı istemek için yan tümceyi kullanıyorsa, sonucun alt sınırındaki garanti artık `omp_get_max_threads` tutamaz.

İşlevin `omp_get_max_threads` geri dönüş değeri, bir sonraki paralel bölgede oluşturulan takımdaki tüm iş parçacıkları için dinamik olarak yeterli depolama alanı ayırmak için kullanılabilir.

#### <a name="cross-references"></a>Çapraz referans

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a><a name="314-omp_get_thread_num-function"></a>3.1.4 omp_get_thread_num fonksiyonu

İşlev, `omp_get_thread_num` iş parçacığının işlevini yürüten iş parçacığının takım içindeki iş parçacığı numarasını döndürür. İş parçacığı numarası 0 `omp_get_num_threads()`ile -1 arasında dır, dahil. Takımın ana iş parçacığı iş parçacığı 0'dır.

Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

Bir seri bölgeden çağrılırsa, `omp_get_thread_num` 0 döndürür. Seri hale getirilmiş iç içe bir paralel bölge içinden çağrılırsa, bu işlev 0 döndürür.

#### <a name="cross-references"></a>Çapraz referans

- [omp_get_num_threads](#312-omp_get_num_threads-function) fonksiyonu

### <a name="315-omp_get_num_procs-function"></a><a name="315-omp_get_num_procs-function"></a>3.1.5 omp_get_num_procs fonksiyonu

İşlev, `omp_get_num_procs` işlevçağrıldığı anda programda kullanılabilen işlemci sayısını döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a><a name="316-omp_in_parallel-function"></a>3.1.6 omp_in_parallel fonksiyonu

İşlev, `omp_in_parallel` paralel olarak işleyen bir paralel bölgenin dinamik kapsamı içinde çağrılırsa sıfır olmayan bir değer döndürür; aksi takdirde, 0 döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

Bu işlev, seri hale getirilmiş iç içe bölgeler de dahil olmak üzere paralel olarak çalışan bir bölge içinden çağrıldığında sıfır olmayan bir değer döndürür.

### <a name="317-omp_set_dynamic-function"></a><a name="317-omp_set_dynamic-function"></a>3.1.7 omp_set_dynamic fonksiyonu

İşlev, `omp_set_dynamic` paralel bölgelerin yürütülmesi için kullanılabilir iş parçacığı sayısının dinamik ayarını sağlar veya devre dışı kılabilir. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

*dynamic_threads* sıfır olmayan bir değere göre değerlendirirse, yaklaşan paralel bölgeleri yürütmek için kullanılan iş parçacığı sayısı, sistem kaynaklarını en iyi şekilde kullanmak için çalışma zamanı ortamı tarafından otomatik olarak ayarlanabilir. Sonuç olarak, kullanıcı tarafından belirtilen iş parçacığı sayısı maksimum iş parçacığı sayısıdır. Paralel bir bölge yürüten takımdaki iş parçacığı sayısı, o paralel bölge boyunca sabit `omp_get_num_threads` kalır ve işlev tarafından bildirilir.

*dynamic_threads 0'a* kadar değerlendirirse, dinamik ayarlama devre dışı bırakılır.

Bu işlev, `omp_in_parallel` işlevin sıfır döndürdüğü programın bir bölümünden çağrıldığında yukarıda açıklanan etkilere sahiptir. `omp_in_parallel` İşlevin sıfır olmayan bir değeri döndürdüğü programın bir bölümünden çağrılırsa, bu işlevin davranışı tanımsız dır.

Çağrının `omp_set_dynamic` ortam değişkeninden `OMP_DYNAMIC` önceliği vardır.

İş parçacıklarının dinamik ayarı için varsayılan uygulama tanımlıdır. Sonuç olarak, doğru yürütme için belirli sayıda iş parçacığına bağlı olan kullanıcı kodları, dinamik iş parçacıklarını açıkça devre dışı bırakmalıdır. Uygulamalar, iş parçacığı sayısını dinamik olarak ayarlama olanağı sağlamak için gerekli değildir, ancak tüm platformlarda taşınabilirliği desteklemek için arabirimi sağlamaları gerekir.

#### <a name="microsoft-specific"></a>Microsoft'a özgü

Mevcut destek `omp_get_dynamic` ve `omp_set_dynamic` aşağıdaki gibidir:

Giriş parametresi `omp_set_dynamic` iş parçacığı ilkesini etkilemez ve iş parçacığı sayısını değiştirmez. `omp_get_num_threads`ayarlanmışsa her zaman kullanıcı tanımlı numarayı veya varsayılan iş parçacığı numarasını döndürür. Geçerli Microsoft uygulamasında, `omp_set_dynamic(0)` varolan iş parçacığı kümesinin aşağıdaki paralel bölge için yeniden kullanılabileceğini, dinamik iş parçacığı işlemini kapatır. `omp_set_dynamic(1)`varolan iş parçacığı kümesini atarak ve yaklaşan paralel bölge için yeni bir küme oluşturarak dinamik iş parçacığı açar. Yeni kümedeki iş parçacığı sayısı eski kümeyle aynıdır ve .'nin geri `omp_get_num_threads`dönüş değerine dayanır. Bu nedenle, en `omp_set_dynamic(0)` iyi performans için varolan iş parçacıklarını yeniden kullanmak için kullanın.

#### <a name="cross-references"></a>Çapraz referans

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a><a name="318-omp_get_dynamic-function"></a>3.1.8 omp_get_dynamic fonksiyonu

İş `omp_get_dynamic` parçacıklarının dinamik ayarı etkinse işlev sıfır olmayan bir değer döndürür ve aksi takdirde 0 döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

Uygulama iş parçacığı sayısının dinamik ayarını uygulamazsa, bu işlev her zaman 0 döndürür. Daha fazla bilgi için [omp_set_dynamic.](#317-omp_set_dynamic-function)

#### <a name="cross-references"></a>Çapraz referans

- Dinamik iş parçacığı ayarı açıklaması için [omp_set_dynamic](#317-omp_set_dynamic-function)bakın.

### <a name="319-omp_set_nested-function"></a><a name="319-omp_set_nested-function"></a>3.1.9 omp_set_nested fonksiyonu

İşlev `omp_set_nested` iç içe paralelliği sağlar veya devre dışı kılabilir. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

*İç içe* geçen ler 0'a göre değerlendirirse, iç içe geçen paralellik devre dışı bırakılır, bu varsayılan dır ve iç içe geçen paralel bölgeler geçerli iş parçacığı tarafından seri hale getirilir ve yürütülür. Aksi takdirde, iç içe paralellik etkindir ve iç içe geçirilmiş paralel bölgeler iç içe takımlar oluşturmak için ek iş parçacıkları dağıtabilir.

Bu işlev, `omp_in_parallel` işlevin sıfır döndürdüğü programın bir bölümünden çağrıldığında yukarıda açıklanan etkilere sahiptir. `omp_in_parallel` İşlevin sıfır olmayan bir değeri döndürdüğü programın bir bölümünden çağrılırsa, bu işlevin davranışı tanımsız dır.

Bu çağrının ortam `OMP_NESTED` değişkeninden önceliği vardır.

İç içe paralellik etkinleştirildiğinde, iç içe paralel bölgeleri yürütmek için kullanılan iş parçacığı sayısı uygulama tanımlı. Sonuç olarak, OpenMP uyumlu uygulamaların iç içe paralellik etkin olsa bile iç içe paralel bölgeleri seri hale getirmek için izin verilir.

#### <a name="cross-references"></a>Çapraz referans

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a><a name="3110-omp_get_nested-function"></a>3.1.10 omp_get_nested fonksiyonu

İç `omp_get_nested` içe paralellik etkinse işlev sıfır olmayan bir değer, devre dışı bırakılırsa 0 döndürür. İç içe paralellik hakkında daha fazla bilgi için [omp_set_nested.](#319-omp_set_nested-function) Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_nested(void);
```

Bir uygulama iç içe paralellik uygulamazsa, bu işlev her zaman 0 döndürür.

## <a name="32-lock-functions"></a>3.2 Kilit fonksiyonları

Bu bölümde açıklanan işlevler eşitleme için kullanılan kilitleri manipüle eder.

Aşağıdaki işlevler için kilit değişkeninin türü `omp_lock_t`olmalıdır. Bu değişkene yalnızca bu işlevler üzerinden erişilmesi gerekir. Tüm kilit işlevleri, işaretçisi `omp_lock_t` türü olan bir bağımsız değişken gerektirir.

- [omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) işlevi basit bir kilidi niçin başlatılmasını öngörür.
- [omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevi basit bir kilidi kaldırır.
- [omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) işlevi basit bir kilit kullanılabilir olana kadar bekler.
- [omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) işlevi basit bir kilit salgılar.
- [omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) işlevi basit bir kilidi sınar.

Aşağıdaki işlevler için kilit değişkeninin türü `omp_nest_lock_t`olmalıdır.  Bu değişkene yalnızca bu işlevler üzerinden erişilmesi gerekir. Tüm nestable kilit işlevleri yazmak için `omp_nest_lock_t` bir işaretçi olan bir bağımsız değişken gerektirir.

- [omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) işlevi nestable kilidi başharfe getirir.
- [omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevi nestable kilidi kaldırır.
- [omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) işlevi, nestable kilidi kullanılabilir olana kadar bekler.
- [omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) işlevi nestable bir kilit salgılar.
- [omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) işlevi nestable kilidi sınar.

OpenMP kilit işlevleri kilit değişkenine her zaman okuyacak ve kilit değişkeninin en güncel değerini güncelleştirebilecekleri şekilde erişir. Bu nedenle, kilit değişkeninin değerinin farklı `flush` iş parçacıkları arasında tutarlı olduğundan emin olmak için bir OpenMP programının açık yönergeler içermesi gerekmez. (Diğer değişkenlerin değerlerini `flush` tutarlı hale getirmek için yönergelere ihtiyaç dgerekebilir.)

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a><a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a>3.2.1 omp_init_lock ve omp_init_nest_lock fonksiyonları

Bu işlevler, bir kilidi başlatmanın tek aracını sağlar. Her işlev, gelecek aramalarda kullanılmak üzere parametre *kilidiyle* ilişkili kilidi niçin başlatılmasını öngörür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

İlk durum kilidi (yani, hiçbir iş parçacığı kilidi sahibi). Nekararlı bir kilit için, ilk iç içe geçme sayısı sıfırdır. Bu yordamlardan herhangi birini, önceden başolarak başlatmış bir kilit değişkeni ile aramak uyumsuz.

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a><a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a>3.2.2 omp_destroy_lock ve omp_destroy_nest_lock fonksiyonları

Bu işlevler, işaretli kilit değişken *kilidi* nin baş harfe ermediğinden emin olun. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Bu yordamlardan herhangi birini, baş harfe sahip olmayan veya kilidi açık bir kilit değişkeni olan bir şekilde aramak uyumsuz.

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a><a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a>3.2.3 omp_set_lock ve omp_set_nest_lock fonksiyonları

Bu işlevlerin her biri belirtilen kilit kullanılabilir olana kadar işlevi yürüten iş parçacığı engeller ve sonra kilidi ayarlar. Kilidi açıksa basit bir kilit kullanılabilir. Kilidi açıksa veya işlevi yürüten iş parçacığına aitse, kararlı bir kilit kullanılabilir. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Basit bir kilit için, `omp_set_lock` işlevin bağımsız değişkeni başharfli kilit değişkenini işaret etmelidir. Kilidin sahipliği, işlevi çalıştıran iş parçacığına verilir.

Nekararlı bir kilit için, `omp_set_nest_lock` işlevin bağımsız değişkeni başharfli bir kilit değişkenini işaret etmelidir. İç içe geçme sayısı artımlı ve iş parçacığı kilidin sahipliğini verir veya tutar.

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a><a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a>3.2.4 omp_unset_lock ve omp_unset_nest_lock fonksiyonlar

Bu işlevler, bir kilidin sahipliğini serbest bırakma nın aracını sağlar. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Bu işlevlerin her biri için bağımsız değişken işlevi yürüten iş parçacığı tarafından sahip olunan bir başharfli kilit değişkeni işaret etmelidir. İş parçacığı bu kilidin sahibi değilse davranış tanımsızdır.

Basit bir kilit `omp_unset_lock` için, işlev kilidin sahipliğinden işlevi yürüten iş parçacığı bültenleri.

Nekararlı bir kilit `omp_unset_nest_lock` için, işlev iç içe geçme sayısını düşürür ve elde edilen sayı sıfırsa işlevi çalıştıran iş parçacığının kilidin sahipliğinden salar.

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a><a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a>3.2.5 omp_test_lock ve omp_test_nest_lock fonksiyonları

Bu işlevler kilit ayarlamaya çalışır, ancak iş parçacığının yürütülmesini engellemez. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Bağımsız değişken, başlanlaşmayan kilit değişkenini işaret etmelidir. Bu işlevler, iş parçacığının yürütülmesini `omp_set_nest_lock`engellemedikleri dışında, kilitleri aynı şekilde `omp_set_lock` ayarlamaya çalışır.

Basit bir kilit `omp_test_lock` için, kilit başarıyla ayarlanırsa işlev sıfır olmayan bir değer döndürür; aksi takdirde, sıfır döndürür.

Nekararlı bir kilit `omp_test_nest_lock` için, kilit başarıyla ayarlanırsa işlev yeni iç içe geçme sayısını döndürür; aksi takdirde, sıfır döndürür.

## <a name="33-timing-routines"></a>3.3 Zamanlama rutinleri

Bu bölümde açıklanan işlevler taşınabilir bir duvar saati zamanlayıcısını destekler:

- [omp_get_wtime](#331-omp_get_wtime-function) işlevi geçen duvar saati saatini döndürür.
- [omp_get_wtick](#332-omp_get_wtick-function) işlevi, birbirini izleyen saat işaretlerinin arasında saniyedöndürür.

### <a name="331-omp_get_wtime-function"></a><a name="331-omp_get_wtime-function"></a>3.3.1 omp_get_wtime fonksiyonu

İşlev, `omp_get_wtime` "geçmişte geçen zaman" süresinden saniyeler içinde geçen duvar saati zamanına eşit çift duyarlıklı kayan nokta değeri döndürür.  Gerçek "geçmişte ki zaman" rasgeledir, ancak uygulama programının yürütülmesi sırasında değişmemesi garanti edilir. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

İşlevin, aşağıdaki örnekte gösterildiği gibi geçen süreleri ölçmek için kullanılması beklenir:

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Döndürülen saatler "iş parçacığı başına süreleri" olan bu süre, bir uygulamaya katılan tüm iş parçacıkları arasında genel olarak tutarlı olmaları gerekmemektedir.

### <a name="332-omp_get_wtick-function"></a><a name="332-omp_get_wtick-function"></a>3.3.2 omp_get_wtick fonksiyonu

İşlev, `omp_get_wtick` birbirini izleyen saat işaretçisi arasındaki saniye sayısına eşit çift duyarlıklı kayan nokta değeri döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
double omp_get_wtick(void);
```

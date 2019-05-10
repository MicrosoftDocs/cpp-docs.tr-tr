---
title: 3. Çalışma zamanı kitaplık işlevleri
ms.date: 01/17/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 3eb6dc4110145a6c45dbdd772deaee3023e68e9d
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525039"
---
# <a name="3-run-time-library-functions"></a>3. Çalışma zamanı kitaplık işlevleri

Bu bölümde OpenMP C ve C++ çalışma zamanı kitaplık işlevleri açıklanmaktadır. Üst bilgi  **\<omp.h >** iki tür, denetlemek ve Paralel yürütme ortamı sorgu ve veri erişimi eşitlemek için kullanılan işlevleri kilitlemek için kullanılan çeşitli işlevleri bildirir.

Türü `omp_lock_t` bir nesne türü bir kilit kullanılabilir gösterebilen ya da bir iş parçacığı bir kilit sahibi. Bu kilitleri olarak ifade edilir *basit kilit*.

Türü `omp_nest_lock_t` ya da, gösterebilen bir nesne türü bir kilit kullanılabilir veya her iki iş parçacığı kimliğine sahip olan kilidi ve *sayısı iç içe* (aşağıda açıklanmıştır). Bu kilitleri olarak ifade edilir *nestable kilit*.

Kitaplık işlevleri, "C" bağlaması olan dış işlevlerdir.

Açıklamalar bu bölümdeki aşağıdaki konularla ayrılır:

- [Yürütme Ortamı işlevleri](#31-execution-environment-functions)
- [Kilit işlevleri](#32-lock-functions)
- [Zamanlama rutinleri](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3.1 yürütme ortamı işlevleri

Bu bölümde açıklanan işlevleri etkiler ve iş parçacıkları, işlemci ve paralel ortam izleyin:

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

### <a name="311-omp_set_num_threads-function"></a>3.1.1 omp_set_num_threads işlevi

`omp_set_num_threads` İşlevi varsayılan belirtmeyin daha sonra paralel bölgeleri için kullanılacak iş parçacığı sayısını ayarlar bir `num_threads` yan tümcesi. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

Parametresinin değeri *num_threads* pozitif bir tamsayı olmalıdır. İş parçacığı sayısını yerleştirmenin dinamik ayarına etkin bağlı etkisini bağlıdır. Kurallar arasındaki etkileşimi hakkında kapsamlı bir dizi için `omp_set_num_threads` işlev ve iş parçacıklarını yerleştirmenin dinamik ayarına bkz [bölümünde 2.3](2-directives.md#23-parallel-construct).

Bu işlev, bir program bölümünden çağrıldığında yukarıda açıklanan etkisi burada `omp_in_parallel` işlev, sıfır döndürür. Bir program bölümünden çağrılırsa burada `omp_in_parallel` işlevi sıfır dışında bir değeri döndürür, bu işlevin davranış tanımlanmamıştır.

Bu çağrı, üzerinde önceliğe sahiptir. `OMP_NUM_THREADS` ortam değişkeni. Çağırarak gerçekleştirilebilir iş parçacığı sayısı için varsayılan değer `omp_set_num_threads` ayarlayarak `OMP_NUM_THREADS` ortam değişkeni, tek bir açıkça geçersiz kılınabilir `parallel` belirterek yönerge `num_threads` yan tümcesi.

#### <a name="cross-references"></a>Çapraz başvuruları

- [omp_set_dynamic](#317-omp_set_dynamic-function) işlevi
- [omp_get_dynamic](#318-omp_get_dynamic-function) işlevi
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) ortam değişkeni
- [num_threads](2-directives.md#23-parallel-construct) yan tümcesi

### <a name="312-omp_get_num_threads-function"></a>3.1.2 omp_get_num_threads işlevi

`omp_get_num_threads` İşlevi döndürür iş parçacığı sayısını şu anda takım içinden çağırıldığında bir paralel bölgenin yürütme. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

`num_threads` Yan tümcesi `omp_set_num_threads` işlevi ve `OMP_NUM_THREADS` ortam değişkeni denetimi bir takım olarak iş parçacığı sayısı.

İş parçacığı sayısı kullanıcı tarafından açıkça ayarlanmamışsa, varsayılan uygulama tarafından tanımlanır. Bu işlev en yakın kapsayan bağlar `parallel` yönergesi. Bu işlev, bir program seri bir kısmını veya serileştirilmiş bir iç içe geçmiş bir paralel bölgenin çağrılırsa, 1 döndürür.

#### <a name="cross-references"></a>Çapraz başvuruları

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [parallel](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a>3.1.3 omp_get_max_threads function

`omp_get_max_threads` İşlevi en az kadar büyük bir paralel bölgenin olmadan, bir takım oluşturmak için kullanılacak iş parçacığı sayısını olması garanti bir tamsayı döndürür bir `num_threads` yan tümcesi olan bu noktada kodda görülebilmesi için. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

Aşağıdaki alt sınırı değeri temel ifade `omp_get_max_threads`:

```

threads-used-for-next-team
<= omp_get_max_threads
```

Paralel bir diğerine, bölge kullandığına dikkat edin `num_threads` iş parçacıklarını garanti sonucunu alt sınırı üzerinde belirli sayıda istek yan tümcesini `omp_get_max_threads` hiçbir uzun tutar.

`omp_get_max_threads` İşlevin dönüş değeri, dinamik olarak sonraki bir paralel bölgenin oluşturulmuş takım tüm iş parçacıkları için yeterli depolama alanı ayırmak için kullanılabilir.

#### <a name="cross-references"></a>Çapraz başvuruları

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a>3.1.4 omp_get_thread_num işlevi

`omp_get_thread_num` İşlevi, iş parçacığı sayısı, kendi takım içindeki işlevi yürüten iş parçacığının döndürür. 0 arasında iş parçacığı numarası kalıyor ve `omp_get_num_threads()`-1, kapsamlı. Takım ana iş parçacığı 0 parçacığıdır.

Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

Bir seri bölgeden çağrılırsa `omp_get_thread_num` 0 döndürür. Serileştirilen iç içe geçmiş bir paralel bölgenin içinde çağrılır, bu işlev 0 döndürür.

#### <a name="cross-references"></a>Çapraz başvuruları

- [omp_get_num_threads](#312-omp_get_num_threads-function) işlevi

### <a name="315-omp_get_num_procs-function"></a>3.1.5 omp_get_num_procs işlevi

`omp_get_num_procs` İşlevi işlevin çağrıldığı zaman programa kullanılabilir işlemci sayısını döndürür. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a>3.1.6 omp_in_parallel işlevi

`omp_in_parallel` İşlevi dinamik kapsam, paralel olarak yürütülen bir paralel bölgenin içinde çağrılırsa sıfır olmayan bir değer döndürür; Aksi takdirde 0 değerini döndürür. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

Bu işlev bir bölge serileştirilme şeklini iç içe geçmiş bölge dahil paralel olarak yürütülen'içinde çağrılır, sıfır olmayan bir değer döndürür.

### <a name="317-omp_set_dynamic-function"></a>3.1.7 omp_set_dynamic işlevi

`omp_set_dynamic` İşlevini etkinleştirir veya paralel bölgeleri yürütülmesi için kullanılabilir iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakır. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

Varsa *dynamic_threads* değerlendirir sıfır olmayan bir değer yaklaşan paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısını otomatik olarak en iyi sistem kaynakları kullanmak için çalışma zamanı ortamı tarafından ayarlanması. Sonuç olarak kullanıcı tarafından belirtilen iş parçacığı sayısı en fazla iş parçacığı sayısıdır. Bir paralel bölgenin yürütme takım iş parçacıkları, paralel bölgenin süresi boyunca sabit kalır ve tarafından bildirilen `omp_get_num_threads` işlevi.

Varsa *dynamic_threads* değerlendirir 0 olarak yerleştirmenin dinamik ayarına devre dışı bırakıldı.

Bu işlev, bir program bölümünden çağrıldığında yukarıda açıklanan etkisi burada `omp_in_parallel` işlev, sıfır döndürür. Bir program bölümünden çağrılırsa burada `omp_in_parallel` işlevi sıfır dışında bir değeri döndürür, bu işlevin davranış tanımlanmamıştır.

Bir çağrı `omp_set_dynamic` üzerinden önceliğe sahip `OMP_DYNAMIC` ortam değişkeni.

Yerleştirmenin dinamik ayarına iş parçacığı sayısı için varsayılan uygulama tanımlanır. Sonuç olarak, belirli bir sayıya doğru yürütme için iş parçacığı bağımlı kullanıcı kodlarını açıkça dinamik iş parçacığı devre dışı bırakmanız gerekir. Uygulamaları iş parçacığı sayısını dinamik olarak ayarlama olanağı sağlamak için gerekli değildir, ancak tüm platformlar arasında taşınabilirlik desteklemek için bir arabirim sağlayacağı şekilde gerekmesinden.

#### <a name="cross-references"></a>Çapraz başvuruları

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a>3.1.8 omp_get_dynamic işlevi

`omp_get_dynamic` İşlevi, iş parçacıkları yerleştirmenin dinamik ayarına etkinleştirilmişse ve 0 döndürür sıfır olmayan bir değer döndürür. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

Uygulama iş parçacığı sayısını yerleştirmenin dinamik ayarına uygulamaz, bu işlev her zaman 0 değerini döndürür.

#### <a name="cross-references"></a>Çapraz başvuruları

- Dinamik iş parçacığı ayarlama ile ilgili açıklama için bkz: [omp_set_dynamic](#317-omp_set_dynamic-function).

### <a name="319-omp_set_nested-function"></a>3.1.9 omp_set_nested işlevi

`omp_set_nested` İşlevini etkinleştirir veya iç içe geçmiş paralellik devre dışı bırakır. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

Varsa *iç içe geçmiş* iç içe geçmiş 0 olarak değerlendirilen paralellik devre dışıysa, varsayılan ve iç içe geçmiş paralel bölgeleri serileştirilmiş ve geçerli iş parçacığı tarafından yürütüldü. Aksi takdirde, iç içe geçmiş paralellik etkin ve iç içe paralel bölgeleri iç içe geçmiş takımlar oluşturmak için ek iş parçacığı dağıtabilir.

Bu işlev, bir program bölümünden çağrıldığında yukarıda açıklanan etkisi burada `omp_in_parallel` işlev, sıfır döndürür. Bir program bölümünden çağrılırsa burada `omp_in_parallel` işlevi sıfır dışında bir değeri döndürür, bu işlevin davranış tanımlanmamıştır.

Bu çağrı, üzerinde önceliğe sahiptir. `OMP_NESTED` ortam değişkeni.

İç içe geçmiş paralellik etkinleştirildiğinde, uygulama tarafından tanımlanan iç içe geçmiş paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı. Sonuç olarak, OpenMP uyumlu uygulamaları, iç içe geçmiş paralellik etkin olsa bile, iç içe geçmiş paralel bölgeleri serileştirmek için izin verilir.

#### <a name="cross-references"></a>Çapraz başvuruları

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a>3.1.10 omp_get_nested işlevi

`omp_get_nested` İşlevi, iç içe geçmiş paralellik etkinse, sıfır dışında bir değeri ile 0 değilse döndürür. İç içe geçmiş paralellik hakkında daha fazla bilgi için bkz. [omp_set_nested](#319-omp_set_nested-function). Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_nested(void);
```

Uygulama iç içe geçmiş paralellik uygulamaz, bu işlev her zaman 0 değerini döndürür.

## <a name="32-lock-functions"></a>3.2 kilit işlevleri

Bu bölümde açıklanan işlevler, eşitleme için kullanılan kilit işleyin.

Aşağıdaki işlevler için kilit değişken türüne sahip olmalıdır `omp_lock_t`. Bu değişken, yalnızca bu işlevleri aracılığıyla erişilmelidir. Tüm kilit işlevleri bir işaretçiye sahip bir bağımsız değişken gerektirir `omp_lock_t` türü.

- [Omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) işlevi basit kilit başlatır.
- [Omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevi basit kilit kaldırır.
- [Omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) işlevi, bir basit kilit kullanılabilir oluncaya kadar bekler.
- [Omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) işlevi basit bir kilidi serbest bırakır.
- [Omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) işlevi, bir basit kilit test.

Aşağıdaki işlevler için kilit değişken türüne sahip olmalıdır `omp_nest_lock_t`.  Bu değişken, yalnızca bu işlevleri aracılığıyla erişilmelidir. Tüm nestable kilit işlevleri bir işaretçiye sahip bir bağımsız değişken gerektirir `omp_nest_lock_t` türü.

- [Omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) işlevi nestable kilit başlatır.
- [Omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevi nestable kilit kaldırır.
- [Omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) işlevi nestable kilit kullanılabilir oluncaya kadar bekler.
- [Omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) işlevi nestable kilit serbest bırakır.
- [Omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) işlevi test nestable kilit.

OpenMP kilit işlevleri kilit değişken bunlar her zaman okuyabilmesini ve en güncel kilit değişkenin değerini güncelleştirme emin bir şekilde erişin. Bu nedenle, açık dahil etmek bir OpenMP program için gerekli değildir `flush` yönergelerini kilit değişkenin değeri farklı iş parçacıkları arasında tutarlı olduğundan emin olun. (İhtiyacı olabilir `flush` diğer değişkenlerin değerlerini tutarlı hale getirmek için yönergeleri.)

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a>3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri

Bu işlevler bir kilit başlatma, yalnızca bir yöntem sağlar. Her işlev parametresi ile ilişkili kilit başlatır *kilit* yaklaşan çağrılarda kullanılmak. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

İlk durum açılmış (diğer bir deyişle, hiçbir iş parçacığı kilit sahibi). Nestable kilit, ilk iç içe geçme sayısı sıfırdır. Zaten başlatılmış bir kilit değişkeniyle bu yordamların birini çağırmaya uyumsuzdur.

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a>3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri

Bu işlevler emin işaret değişkeni kilitlemek için *kilit* başlatılmadı. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Başlatılmamış bir kilit değişkeniyle bu yordamların birini çağırmak için uyumsuz ya da kilitli olduğu.

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a>3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri

Bu işlevlerin her biri, belirtilen kilit kullanılabilir ve ardından kilit ayarlar kadar işlevi yürütme iş parçacığını engeller. Basit bir kilit, varsa kullanılabilir kilidi. Nestable kilit, varsa kullanılabilir kilidi veya işlev yürütme iş parçacığı tarafından zaten sahiplenilmiş. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Basit bir kilit, bağımsız değişkeni için `omp_set_lock` işlevi bir başlatılmış kilit değişkene işaret etmelidir. Kilidi sahipliğini, işlevi yürütme iş parçacığı için verilir.

Nestable kilit, bağımsız değişkeni için `omp_set_nest_lock` işlevi bir başlatılmış kilit değişkene işaret etmelidir. İç içe geçme sayısının artırılması ve iş parçacığı verilir veya kilidi sahipliğini tutar.

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a>3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri

Bu işlevler bir kilidin sahipliğini serbest bir yöntem sağlar. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Bu işlevlerin her biri bağımsız değişken, işlev yürütme iş parçacığı tarafından sahip olunan bir başlatılmış kilit değişkenine işaret etmelidir. İş parçacığı bu kilide sahip değilse davranış tanımlanmamıştır.

Basit bir kilitleme `omp_unset_lock` işlevi kilidi sahipliğini işlev yürütme iş parçacığını serbest bırakır.

Bir nestable kilit için `omp_unset_nest_lock` işlev iç içe geçme sayısı ve yayınlar sonuç sayısı sıfır ise, işlev kilidi sahipliğini yürüten iş parçacığının azaltır.

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a>3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri

Bu işlevler bir kilidi ayarlama girişiminde bulunuldu ancak iş parçacığının yürütülmesini engelleme. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Bağımsız değişken bir başlatılmış kilit değişkene işaret etmelidir. Bu işlevler, aynı şekilde kilit ayarlama girişimi `omp_set_lock` ve `omp_set_nest_lock`, bunlar iş parçacığının yürütülmesini engelleme hariç aynıdırlar.

Basit bir kilitleme `omp_test_lock` işlevi lock başarılı bir şekilde ayarlanmışsa sıfır olmayan bir değer döndürür; Aksi takdirde, sıfır döndürür.

Bir nestable kilit için `omp_test_nest_lock` işlevi lock başarılı bir şekilde ayarlanmışsa yeni iç içe geçme sayısını döndürür; Aksi takdirde, sıfır döndürür.

## <a name="33-timing-routines"></a>3.3 zamanlama rutinleri

Bu bölümde açıklanan işlevler bir taşınabilir duvar saati Zamanlayıcı destekler:

- [Omp_get_wtime](#331-omp_get_wtime-function) geçen duvar saati zamanı işlevi döndürür.
- [Omp_get_wtick](#332-omp_get_wtick-function) işlevi art arda gelen saatin tik takları saniye döndürür.

### <a name="331-omp_get_wtime-function"></a>3.3.1 omp_get_wtime işlevi

`omp_get_wtime` İşlevi döndürür çift duyarlıklı kayan noktalı değeri eşittir geçen duvar saati süresi içinde bazı "zamanda" geçmiş beri geçen saniye sayısı.  Gerçek "süresi geçmiş" isteğe bağlıdır, ancak uygulama programın yürütülmesi sırasında değiştirmemesi garantisi. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

Bu işlev, aşağıdaki örnekte gösterildiği gibi geçen süreleri ölçmek için kullanılacak beklenen:

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Döndürülen süreleri, bir uygulamada katılan tüm iş parçacıkları arasında genel olarak tutarlı olması için gerekli olmayan yöneliktir tarafından "iş parçacığı başına saatleri" formundadır.

### <a name="332-omp_get_wtick-function"></a>3.3.2 omp_get_wtick işlevi

`omp_get_wtick` İşlevi döndürür çift duyarlıklı kayan noktalı değeri saniye sayısını eşit art arda gelen saatin tik takları. Biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
double omp_get_wtick(void);
```

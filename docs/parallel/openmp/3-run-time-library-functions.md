---
description: 'Hakkında daha fazla bilgi edinin: 3. Çalışma zamanı kitaplık işlevleri'
title: 3. Çalışma zamanı kitaplık işlevleri
ms.date: 05/13/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 67eb3b25efd65dcb99cd140bdc4e93491bacd79a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342562"
---
# <a name="3-run-time-library-functions"></a>3. çalışma zamanı kitaplık işlevleri

Bu bölümde, OpenMP C ve C++ çalışma zamanı kitaplığı işlevleri açıklanmaktadır. Üst bilgi **\<omp.h>** iki tür bildirir, paralel yürütme ortamını denetlemek ve sorgulamak için kullanılabilen çeşitli işlevler ve verilere erişimi eşzamanlı hale getirmek için kullanılabilecek işlevleri kilitler.

Tür, bir `omp_lock_t` kilidin kullanılabilir olduğunu veya bir iş parçacığının bir kilide sahip olduğunu temsil eden bir nesne türüdür. Bu kilitler *basit kilitler* olarak adlandırılır.

Türü, `omp_nest_lock_t` bir kilidin kullanılabilir olduğunu veya kilit sahibi olan iş parçacığının kimliğini ve *iç içe bir sayımı* (aşağıda açıklanmıştır) temsil eden bir nesne türüdür. Bu kilitler, *iç içe konulabilir kilitler* olarak adlandırılır.

Kitaplık işlevleri "C" bağlantısıyla dış işlevlerdir.

Bu bölümdeki açıklamalar aşağıdaki konulara bölünmüştür:

- [Yürütme ortamı işlevleri](#31-execution-environment-functions)
- [Lock işlevleri](#32-lock-functions)
- [Zamanlama yordamları](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3,1 yürütme ortamı işlevleri

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

### <a name="311-omp_set_num_threads-function"></a><a name="311-omp_set_num_threads-function"></a> 3.1.1 omp_set_num_threads işlevi

`omp_set_num_threads`İşlevi, yan tümce belirtmeyen daha sonra paralel bölgeler için kullanılacak varsayılan iş parçacığı sayısını ayarlar `num_threads` . Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

*Num_threads* parametresinin değeri pozitif bir tamsayı olmalıdır. Etkisi, iş parçacığı sayısının dinamik ayarlamasının etkin olup olmamasına bağlıdır. İş parçacıklarının işlev ve dinamik ayarlaması arasındaki etkileşim hakkında kapsamlı bir kurallar kümesi için `omp_set_num_threads` bkz. [Bölüm 2,3](2-directives.md#23-parallel-construct).

Bu işlev, işlevin sıfır döndürdüğünden programın bir kısmından çağrıldığında yukarıda açıklanan etkileri vardır `omp_in_parallel` . `omp_in_parallel`İşlevin sıfır dışında bir değer döndürdüğü programın bir kısmından çağrılırsa, bu işlevin davranışı tanımsızdır.

Bu çağrının ortam değişkenine göre önceliği vardır `OMP_NUM_THREADS` . ' İ çağırarak veya ortam değişkeni ayarlanarak kurulabilen iş parçacığı sayısının varsayılan değeri, `omp_set_num_threads` `OMP_NUM_THREADS` yan tümcesini belirterek tek bir yönergede açıkça geçersiz kılınabilir `parallel` `num_threads` .

Daha fazla bilgi için bkz. [omp_set_dynamic](#317-omp_set_dynamic-function).

#### <a name="cross-references"></a>Çapraz başvurular

- [omp_set_dynamic](#317-omp_set_dynamic-function) işlevi
- [omp_get_dynamic](#318-omp_get_dynamic-function) işlevi
- [Omp_num_threads](4-environment-variables.md#42-omp_num_threads) ortam değişkeni
- [num_threads](2-directives.md#23-parallel-construct) yan tümcesi

### <a name="312-omp_get_num_threads-function"></a><a name="312-omp_get_num_threads-function"></a> 3.1.2 omp_get_num_threads işlevi

İşlevi, bir `omp_get_num_threads` ekipte Şu anda çağrıldığı paralel bölgeyi yürüten iş parçacıklarının sayısını döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

`num_threads`Yan tümce, `omp_set_num_threads` işlev ve `OMP_NUM_THREADS` ortam değişkeni, bir ekipteki iş parçacığı sayısını denetler.

İş parçacığı sayısı Kullanıcı tarafından açıkça ayarlanmamışsa, varsayılan değer uygulama tanımlı ' dır. Bu işlev en yakın kapsayan yönergeyi bağlar `parallel` . Bir programın seri kısmından veya serileştirilmiş bir paralel bölgeden çağrılırsa, bu işlev 1 döndürür.

Daha fazla bilgi için bkz. [omp_set_dynamic](#317-omp_set_dynamic-function).

#### <a name="cross-references"></a>Çapraz başvurular

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [dir](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a><a name="313-omp_get_max_threads-function"></a> 3.1.3 omp_get_max_threads işlevi

`omp_get_max_threads`İşlev, bir ekip oluşturmak için kullanılan iş parçacıklarının sayısı en az, bir yan tümce olmayan bir paralel bölgenin, `num_threads` koddaki bu noktada görülebilmesi halinde bir tamsayı döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

Aşağıdaki değer üzerinde bir alt sınır ifade eder `omp_get_max_threads` :

> *iş parçacıkları-kullanılan-Next-Team* <= `omp_get_max_threads`

Başka bir paralel bölge, `num_threads` belirli sayıda iş parçacığı istemek için yan tümcesini kullanıyorsa, sonucun alt sınır ile elde edilmesine dair garantiyi unutmayın `omp_get_max_threads` .

`omp_get_max_threads`İşlevin dönüş değeri, bir sonraki paralel bölgede oluşturulan ekipteki tüm iş parçacıkları için yeterli depolama alanını dinamik olarak ayırmak için kullanılabilir.

#### <a name="cross-references"></a>Çapraz başvurular

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a><a name="314-omp_get_thread_num-function"></a> 3.1.4 omp_get_thread_num işlevi

`omp_get_thread_num`İşlevi, işlevini yürüten iş parçacığının ekibi içindeki iş parçacığı numarasını döndürür. İş parçacığı sayısı 0 ile `omp_get_num_threads()` -1 (dahil) arasındadır. Ekibin ana iş parçacığı iş parçacığı 0 ' dır.

Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

Bir seri bölgesinden çağrılırsa `omp_get_thread_num` 0 döndürür. Seri hale getirilen bir paralel bölgenin içinden çağrılırsa, bu işlev 0 döndürür.

#### <a name="cross-references"></a>Çapraz başvurular

- [omp_get_num_threads](#312-omp_get_num_threads-function) işlevi

### <a name="315-omp_get_num_procs-function"></a><a name="315-omp_get_num_procs-function"></a> 3.1.5 omp_get_num_procs işlevi

`omp_get_num_procs`İşlevi, işlev çağrıldığında programın kullanabileceği işlemcilerin sayısını döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a><a name="316-omp_in_parallel-function"></a> 3.1.6 omp_in_parallel işlevi

İşlevi, paralel `omp_in_parallel` olarak yürütülen paralel bölgenin dinamik kapsamı içinde çağrılırsa sıfır dışında bir değer döndürür; Aksi takdirde, 0 döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

Bu işlev, seri hale getirilen iç içe geçmiş bölgeler de dahil olmak üzere paralel olarak çalıştırılan bir bölgenin içinden çağrıldığında sıfır dışında bir değer döndürür.

### <a name="317-omp_set_dynamic-function"></a><a name="317-omp_set_dynamic-function"></a> 3.1.7 omp_set_dynamic işlevi

`omp_set_dynamic`İşlevi, paralel bölgelerin yürütülmesi için kullanılabilen iş parçacığı sayısının dinamik olarak ayarlanmasını mümkün veya devre dışı bırakır. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

*Dynamic_threads* sıfır dışında bir değere değerlendirilirse, yaklaşan paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı, sistem kaynaklarını en iyi şekilde kullanmak için çalışma zamanı ortamı tarafından otomatik olarak ayarlanabilir. Sonuç olarak, Kullanıcı tarafından belirtilen iş parçacıklarının sayısı en fazla iş parçacığı sayısıdır. Bir paralel bölgeyi yürüten ekipteki iş parçacığı sayısı, bu paralel bölgenin süresince sabit kalır ve işlev tarafından raporlanır `omp_get_num_threads` .

*Dynamic_threads* 0 olarak değerlendirilirse, dinamik ayarlama devre dışı bırakılır.

Bu işlev, işlevin sıfır döndürdüğünden programın bir kısmından çağrıldığında yukarıda açıklanan etkileri vardır `omp_in_parallel` . `omp_in_parallel`İşlevin sıfır dışında bir değer döndürdüğü programın bir kısmından çağrılırsa, bu işlevin davranışı tanımsızdır.

Bir çağrısının `omp_set_dynamic` ortam değişkenine göre önceliği vardır `OMP_DYNAMIC` .

İş parçacıklarının dinamik ayarlaması için varsayılan değer uygulama tanımlı ' dır. Sonuç olarak, doğru yürütme için belirli sayıda iş parçacığına bağlı olan kullanıcı kodları dinamik iş parçacıklarını açıkça devre dışı bırakmalıdır. Uygulamaların iş parçacığı sayısını dinamik olarak ayarlayabilme olanağı sağlaması gerekmez, ancak tüm platformlarda taşınabilirliği desteklemek için arabirimin sağlanması gerekir.

#### <a name="microsoft-specific"></a>Microsoft'a özgü

Ve için geçerli desteği `omp_get_dynamic` `omp_set_dynamic` aşağıdaki gibidir:

İçin giriş parametresi, `omp_set_dynamic` iş parçacığı ilkesini etkilemez ve iş parçacığı sayısını değiştirmez. `omp_get_num_threads` her zaman, ayarlandıysa, Kullanıcı tanımlı sayı veya varsayılan iş parçacığı numarasını döndürür. Geçerli Microsoft uygulamasında, `omp_set_dynamic(0)` mevcut iş parçacığı kümesinin aşağıdaki paralel bölgede yeniden kullanılabilmesi için dinamik iş parçacığını devre dışı bırakır. `omp_set_dynamic(1)` Mevcut iş parçacığı kümesini atarak ve yaklaşan paralel bölge için yeni bir küme oluşturarak dinamik iş parçacığını etkinleştirir. Yeni küme içindeki iş parçacıklarının sayısı, eski küme ile aynıdır ve dönüş değerine göre belirlenir `omp_get_num_threads` . Bu nedenle, en iyi performans için, `omp_set_dynamic(0)` mevcut iş parçacıklarını yeniden kullanmak üzere kullanın.

#### <a name="cross-references"></a>Çapraz başvurular

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a><a name="318-omp_get_dynamic-function"></a> 3.1.8 omp_get_dynamic işlevi

`omp_get_dynamic`İşlev, dinamik iş parçacığı ayarlamasının etkin olması durumunda sıfır dışında bir değer döndürür ve aksi takdirde 0 döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

Uygulama iş parçacığı sayısı için dinamik ayarlama gerçekleştirmezse, bu işlev her zaman 0 döndürür. Daha fazla bilgi için bkz. [omp_set_dynamic](#317-omp_set_dynamic-function).

#### <a name="cross-references"></a>Çapraz başvurular

- Dinamik iş parçacığı ayarlamasının açıklaması için bkz. [omp_set_dynamic](#317-omp_set_dynamic-function).

### <a name="319-omp_set_nested-function"></a><a name="319-omp_set_nested-function"></a> 3.1.9 omp_set_nested işlevi

`omp_set_nested`İşlevi iç içe paralelliği devre dışı bırakır veya devre dışı bırakır. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

*İç içe* 0 olarak değerlendirilirse, iç içe paralellik devre dışı bırakılır, varsayılan ve iç içe paralel bölgeler geçerli iş parçacığı tarafından serileştirilir ve yürütülür. Aksi takdirde, iç içe paralellik etkindir ve iç içe yerleştirilmiş olan paralel bölgeler, iç içe takımlar oluşturmak için ek iş parçacıkları dağıtabilir.

Bu işlev, işlevin sıfır döndürdüğünden programın bir kısmından çağrıldığında yukarıda açıklanan etkileri vardır `omp_in_parallel` . `omp_in_parallel`İşlevin sıfır dışında bir değer döndürdüğü programın bir kısmından çağrılırsa, bu işlevin davranışı tanımsızdır.

Bu çağrının ortam değişkenine göre önceliği vardır `OMP_NESTED` .

İç içe paralel paralellik etkinleştirildiğinde, iç içe paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı uygulama tanımlı olur. Sonuç olarak, OpenMP uyumlu uygulamaların iç içe paralel bölgeleri seri hale getirilmiş paralellik etkin olduğunda bile serileştirmek için izin verilir.

#### <a name="cross-references"></a>Çapraz başvurular

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a><a name="3110-omp_get_nested-function"></a> 3.1.10 omp_get_nested işlevi

`omp_get_nested`İşlev, iç içe paralellik etkinse ve devre dışıysa 0 olarak sıfır olmayan bir değer döndürür. İç içe paralellik hakkında daha fazla bilgi için bkz. [omp_set_nested](#319-omp_set_nested-function). Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_get_nested(void);
```

Bir uygulama iç içe paralellik uygulamaz, bu işlev her zaman 0 değerini döndürür.

## <a name="32-lock-functions"></a>3,2 kilit işlevleri

Bu bölümde açıklanan işlevler, eşitleme için kullanılan kilitleri işleme.

Aşağıdaki işlevler için, kilit değişkeninin türü olmalıdır `omp_lock_t` . Bu değişkene yalnızca bu işlevlerden erişilmesi gerekir. Tüm kilit işlevleri, türüne işaretçi olan bir bağımsız değişken gerektirir `omp_lock_t` .

- [Omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) işlevi bir basit kilit başlatır.
- [Omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevi basit bir kilidi kaldırır.
- [Omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) işlevi, basit bir kilit kullanılabilir olana kadar bekler.
- [Omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) işlevi basit bir kilit yayınlar.
- [Omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) işlevi basit bir kilidi sınar.

Aşağıdaki işlevler için, kilit değişkeninin türü olmalıdır `omp_nest_lock_t` .  Bu değişkene yalnızca bu işlevlerden erişilmesi gerekir. Tüm iç içe konulabilir Lock işlevleri, türüne işaretçi olan bir bağımsız değişken gerektirir `omp_nest_lock_t` .

- [Omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) işlevi bir iç içe konulabilir kilit başlatır.
- [Omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) işlevi bir iç içe konulabilir kilidi kaldırır.
- [Omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) işlevi, bir iç içe konulabilir kilit kullanılabilir olana kadar bekler.
- [Omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) işlevi bir iç içe konulabilir kilit yayınlar.
- [Omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) işlevi bir iç içe konulabilir kilidi sınar.

OpenMP Lock işlevleri kilit değişkenine her zaman bir kilit değişkeninin en güncel değerini okuyup güncelleştirdikleri şekilde erişir. Bu nedenle, bir OpenMP programının `flush` , kilit değişkeninin değerinin farklı iş parçacıkları arasında tutarlı olduğundan emin olmak için açık yönergeler içermesi gerekmez. ( `flush` Diğer değişkenlerin değerlerini tutarlı hale getirme yönergeleri için bir gereksinim olabilir.)

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a><a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a> 3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri

Bu işlevler, bir kilit başlatma yöntemi sağlar. Her işlev, yaklaşan çağrılarında kullanılmak üzere parametre *kilidi* ile ilişkili kilidi başlatır. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

Başlangıç durumunun kilidi açıldı (diğer bir deyişle, kilidin sahibi olan iş parçacığı yok). Bir iç içe konulabilir kilit için, ilk iç içe geçme sayısı sıfırdır. Önceden başlatılmış bir kilit değişkeniyle bu yordamların her birini çağırmak uyumlu değildir.

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a><a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a> 3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri

Bu işlevler, kilit değişkeni *kilidinin* işaret edilen başlatılmamış olduğundan emin olur. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Başlatılmamış veya kilidi açılmış bir kilit değişkeniyle bu yordamların her birini çağırmak uyumlu değildir.

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a><a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a> 3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri

Bu işlevlerin her biri, belirtilen kilit kullanılabilir olana kadar işlevi yürüten iş parçacığını engeller ve sonra kilidi ayarlar. Kilidi açıldığında basit bir kilit vardır. Bir iç içe konulabilir kilidi, kilidi açıksa veya işlevi yürüten iş parçacığına zaten aitse kullanılabilir. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Basit bir kilit için, işlevin bağımsız değişkeni `omp_set_lock` başlatılmış bir kilit değişkenine işaret etmelidir. Kilit sahipliği, işlevi yürüten iş parçacığına verilir.

Bir iç içe konulabilir kilit için, işlevin bağımsız değişkeni `omp_set_nest_lock` başlatılmış bir kilit değişkenine işaret etmelidir. İç içe geçme sayısı artırılır ve iş parçacığı, kilidin sahipliğine sahiptir veya devam eder.

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a><a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a> 3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri

Bu işlevler, bir kilidin sahipliğini serbest bırakma araçlarını sağlar. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Bu işlevlerin her biri için bağımsız değişken, işlevi yürüten iş parçacığının sahip olduğu başlatılmış bir kilit değişkenine işaret etmelidir. İş parçacığı bu kilide yoksa davranış tanımsızdır.

Basit bir kilit için işlev, `omp_unset_lock` kilit sahipünden işlevi yürüten iş parçacığını serbest bırakır.

İç içe konulabilir bir kilit için işlev, `omp_unset_nest_lock` iç içe geçmiş sayıyı azaltır ve elde edilen sayı sıfır ise, işlevi yürüten iş parçacığını kilit sahipünden bırakır.

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a><a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a> 3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri

Bu işlevler, bir kilit ayarlamaya çalışır ancak iş parçacığının yürütülmesini engellemez. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Bağımsız değişken, başlatılmış bir kilit değişkenine işaret etmelidir. Bu işlevler, `omp_set_lock` `omp_set_nest_lock` iş parçacığının yürütülmesini engelolmadıklarından, ve ile aynı şekilde bir kilit ayarlamaya çalışır.

Basit bir kilit için, `omp_test_lock` Kilit başarıyla ayarlandıysa işlev sıfır dışında bir değer döndürür; Aksi takdirde, sıfır döndürür.

Bir iç içe konulabilir kilit için, `omp_test_nest_lock` Kilit başarıyla ayarlandıysa işlev yeni iç içe geçme sayısını döndürür; Aksi takdirde, sıfır döndürür.

## <a name="33-timing-routines"></a>3,3 zamanlama yordamları

Bu bölümde açıklanan işlevler, taşınabilir bir duvar saati zamanlayıcısını destekler:

- [Omp_get_wtime](#331-omp_get_wtime-function) işlevi geçen duvar saati saati döndürür.
- [Omp_get_wtick](#332-omp_get_wtick-function) işlevi, ardışık saat işaretleri arasındaki saniyeleri döndürür.

### <a name="331-omp_get_wtime-function"></a><a name="331-omp_get_wtime-function"></a> 3.3.1 omp_get_wtime işlevi

`omp_get_wtime`İşlevi, "geçmişteki" bir süre sonra geçen duvar saati zamanına eşit bir çift duyarlıklı kayan nokta değeri döndürür.  Gerçek "geçmişteki süre" değeri rastgele, ancak uygulama programının yürütülmesi sırasında değişmemelidir. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

İşlevin, aşağıdaki örnekte gösterildiği gibi geçen süreleri ölçmek için kullanılması tahmin edilir:

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Döndürülen süreler, bir uygulamaya katılan tüm iş parçacıkları genelinde küresel olarak tutarlı olması gerekmediği anlamına gelen "iş parçacığı başına zamanlardır".

### <a name="332-omp_get_wtick-function"></a><a name="332-omp_get_wtick-function"></a> 3.3.2 omp_get_wtick işlevi

`omp_get_wtick`İşlevi, ardışık saat işaretleri arasındaki saniye sayısına eşit bir çift duyarlıklı kayan nokta değeri döndürür. Bunun biçimi aşağıdaki gibidir:

```cpp
#include <omp.h>
double omp_get_wtick(void);
```

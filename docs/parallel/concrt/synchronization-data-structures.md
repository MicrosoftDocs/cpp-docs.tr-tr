---
title: Eşitleme Veri Yapıları
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: f9b949e7782c4b9ca302e9e623ce5f09061c39ef
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301889"
---
# <a name="synchronization-data-structures"></a>Eşitleme Veri Yapıları

Eşzamanlılık Çalışma zamanı birden fazla iş parçacığından Paylaşılan verilere erişimi eşitleme olanak tanıyan çeşitli veri yapıları sağlar. Bu veri yapıları, paylaşılan sık değişiklik verilerine sahip olduğunda yararlıdır. Bir eşitleme nesnesi olan kritik bölümü gibi diğer iş parçacıklarını paylaşılan kaynağı kullanılabilir hale gelene kadar beklenecek neden olur. Bu nedenle, sık kullanılan veri erişimi eşitlemek için böyle bir nesnenin kullanırsanız, uygulamanızda ölçeklenebilirlik kaybedebilir. [Paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) sağlar [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını, bir kaynağın birden çok iş parçacığı veya eşitleme gerek kalmadan görevler arasında paylaşmanıza olanak tanır. Hakkında daha fazla bilgi için `combinable` sınıfı [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

##  <a name="top"></a> Bölümleri

Bu konuda ayrıntılı aşağıdaki zaman uyumsuz ileti blok türleri açıklanmaktadır:

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock ve scoped_lock_read](#scoped_lock)

- [event](#event)

##  <a name="critical_section"></a> critical_section

[Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfı temsil eder bir işbirlikçi karşılıklı dışlama nesnesini bunları öncelik verme yerine diğer görevlere verir. Kritik bölümler birden çok iş parçacığı özel okuma ve yazma erişimi Paylaşılan verilere gerektiğinde kullanışlıdır.

`critical_section` Reentrant olmayan bir sınıftır. [Concurrency::critical_section::lock](reference/critical-section-class.md#lock) yöntemi türünde bir özel durum atar [concurrency::improper_lock](../../parallel/concrt/reference/improper-lock-class.md) kilidi zaten sahip olan bir iş parçacığı tarafından çağrılırsa.

### <a name="methods-and-features"></a>Yöntemleri ve özellikleri

Aşağıdaki tabloda tanımlanır önemli yöntemler gösterilmektedir `critical_section` sınıfı.

|Yöntem|Açıklama|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|Kritik bölüm devralır. Kilit alması kadar arama bağlamı engeller.|
|[try_lock](reference/critical-section-class.md#try_lock)|Kritik bölüm almaya çalışır ancak engelleme yapmadığından.|
|[Kilit açma](reference/critical-section-class.md#unlock)|Kritik bölüm serbest bırakır.|

[[Üst](#top)]

##  <a name="reader_writer_lock"></a> reader_writer_lock

[Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) sınıfı, Paylaşılan verilere iş parçacığı açısından güvenli okuma/yazma işlemleri sağlar. Birden çok iş parçacığı paylaşılan bir kaynağa eş zamanlı okuma erişimi gerektirir, ancak paylaşılan bir kaynağa nadiren yazma Okuyucu/Yazıcı kilitleri kullanın. Bu sınıf, bir nesneye herhangi bir zamanda yalnızca bir iş parçacığı yazma erişim sağlar.

`reader_writer_lock` Sınıfı gerçekleştirebilir daha iyi `critical_section` çünkü bir `critical_section` nesne eş zamanlı okuma erişimi engelleyen bir paylaşılan kaynağa özel erişim alır.

Gibi `critical_section` sınıfı `reader_writer_lock` sınıfı temsil eder bir işbirlikçi karşılıklı dışlama nesnesini bunları öncelik verme yerine diğer görevlere verir.

Paylaşılan bir kaynağa yazmanız gereken bir iş parçacığı bir Okuyucu/Yazıcı kilidi alır, ayrıca kaynağa erişmesi gereken başka iş parçacıklarının yazıcı kilidi serbest bırakır kadar engellenir. `reader_writer_lock` Sınıfı, örneği bir *yazma tercih* önce bekleyen okuyucular kaldırır, bekleme yazıcılar engellemesinin kaldırıldığı bir kilidi kilidinin süresidir.

Gibi `critical_section` sınıfı `reader_writer_lock` reentrant olmayan bir sınıftır. [Concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock) ve [concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read) yöntemleri türünde bir özel durum throw `improper_lock` sahibi zaten bir iş parçacığı tarafından çağrılırsa Kilit.

> [!NOTE]
>  Çünkü `reader_writer_lock` sınıftır reentrant olmayan, bir salt okunur kilidi için bir Okuyucu/Yazıcı kilidi yükseltme veya düşürme bir salt okunur kilidi için bir Okuyucu/Yazıcı kilidi. Bu işlemlerin gerçekleştirme belirtilmeyen bir davranış üretir.

### <a name="methods-and-features"></a>Yöntemleri ve özellikleri

Aşağıdaki tabloda tanımlanır önemli yöntemler gösterilmektedir `reader_writer_lock` sınıfı.

|Yöntem|Açıklama|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|Okuma/yazma erişimi kilidi alır.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Kilit okuma/yazma erişim kazanmak çalışır, ancak engelleme yapmadığından.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Salt okunur kilidi alır.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Kilit salt okunur erişim kazanmak çalışır, ancak engelleme yapmadığından.|
|[Kilit açma](reference/reader-writer-lock-class.md#unlock)|Kilidi serbest bırakır.|

[[Üst](#top)]

##  <a name="scoped_lock"></a> scoped_lock ve scoped_lock_read

`critical_section` Ve `reader_writer_lock` sınıfları karşılıklı dışlama nesneleriyle çalışma biçiminizi basitleştirin. iç içe geçmiş yardımcı sınıfları sağlar. Bu yardımcı sınıfları olarak bilinen *kilit kapsamı*.

`critical_section` Sınıfı içeren [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) sınıfı. Erişim için sağlanan Oluşturucu edinme `critical_section` nesne; o nesnenin yok Edicisi yayınlar erişim. `reader_writer_lock` Sınıfı içeren [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) benzer sınıfı `critical_section::scoped_lock`sağlanan yazma erişimi yönetir, dışında `reader_writer_lock` nesne. `reader_writer_lock` Sınıfı da içeren [concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) sınıfı. Bu sınıf sağlanan okuma erişimini yönetir `reader_writer_lock` nesne.

Kapsamlı kilit ile çalışırken çeşitli avantajlar sağlayan `critical_section` ve `reader_writer_lock` el ile nesneleri. Genellikle, kapsamlı bir kilit yığında ayırın. Bunu kaldırıldığında kapsamlı bir kilit, karşılıklı dışlama nesnesine erişimi otomatik olarak serbest bırakır; Bu nedenle, el ile temel alınan nesnede kilidini değil. Birden çok işlevi içeriyor gerektiğinde bu faydalıdır `return` deyimleri. Kapsamlı kilitleri da özel durum-güvenli kod yazmanıza yardımcı olabilir. Olduğunda bir `throw` deyimi neden olan yığının geriye doğru izlemek, herhangi bir etkin kapsamlı kilidi yok Edicisi çağrılır ve bu nedenle karşılıklı dışlama nesne her zaman doğru bir şekilde serbest.

> [!NOTE]
>  Kullanırken `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, ve `reader_writer_lock::scoped_lock_read` sınıfları değil el ile sürüm temel alınan karşılıklı dışlama nesnesine erişim. Bu, çalışma zamanı geçersiz bir durumda koyabilirsiniz.

##  <a name="event"></a> Olay

[Concurrency::event](../../parallel/concrt/reference/event-class.md) sınıf durumu sinyal ya da verilmemiş bir eşitleme nesnesi temsil eder. Paylaşılan verilere erişimi korumanın amacı olan, kritik bölüm gibi eşitleme nesneleri aksine, yürütmenin akışını olayları eşitleyin.

`event` Sınıfı, başka bir görev için iş bir görev tamamlandığında yararlıdır. Örneğin, bir görev, verileri bir ağ bağlantısı veya bir dosyadan okuma izni olduğunu başka bir görevi sinyal.

### <a name="methods-and-features"></a>Yöntemleri ve özellikleri

Aşağıdaki tabloda çeşitli tarafından tanımlanan önemli yöntemler gösterilmektedir `event` sınıfı.

|Yöntem|Açıklama|
|------------|-----------------|
|[bekleme](reference/event-class.md#wait)|Olayın sinyal haline bekler.|
|[set](reference/event-class.md#set)|Olayın sinyal durumuna ayarlar.|
|[Sıfırlama](reference/event-class.md#reset)|Olay verilmemiş durumuna ayarlar.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Birden fazla olayın sinyal haline bekler.|

### <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek için `event` sınıfı [eşitleme veri yapılarını Windows API ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Üst](#top)]

## <a name="related-sections"></a>İlgili Bölümler

[Eşitleme Veri Yapılarını Windows API ile Karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Eşitleme veri yapılarını Windows API'sı tarafından sağlanan davranışını karşılaştırır.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
Eşzamanlılık paralel programlama basitleştirir ve ilgili konulara bağlantılar içeren çalışma zamanı, açıklar.

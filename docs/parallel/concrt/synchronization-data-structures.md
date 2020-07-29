---
title: Eşitleme Veri Yapıları
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: 244aaac9bd40c83d0bbec3c360bdf7351da54baf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231669"
---
# <a name="synchronization-data-structures"></a>Eşitleme Veri Yapıları

Eşzamanlılık Çalışma Zamanı, birden çok iş parçacığından paylaşılan verilere erişimi eşitlemenize olanak sağlayan çeşitli veri yapıları sağlar. Bu veri yapıları, seyrek olarak değiştirdiğiniz verileri paylaştığınız zaman yararlıdır. Bir eşitleme nesnesi, Örneğin kritik bir bölüm, diğer iş parçacıklarının paylaşılan kaynak kullanılabilir olana kadar beklemesini sağlar. Bu nedenle, sık kullanılan verilere erişimi eşleştirmek için böyle bir nesne kullanırsanız, uygulamanızda ölçeklenebilirliği kaybedebilirsiniz. [Paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) , eşitlemeye gerek olmadan bir kaynağı birçok iş parçacığı veya görev arasında paylaşmanızı sağlayan [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını sağlar. Sınıfı hakkında daha fazla bilgi için `combinable` bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="sections"></a><a name="top"></a>Başlıklı

Bu konuda, aşağıdaki zaman uyumsuz ileti bloğu türleri ayrıntılı olarak açıklanmaktadır:

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock ve scoped_lock_read](#scoped_lock)

- [olay](#event)

## <a name="critical_section"></a><a name="critical_section"></a>critical_section

[Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfı, öncelik verme yerine diğer görevlere veren bir işbirlikçi karşılıklı dışlama nesnesini temsil eder. Kritik bölümler, birden çok iş parçacığının paylaşılan verilere özel okuma ve yazma erişimi gerektirmesi durumunda faydalıdır.

`critical_section`Sınıf yer yok. [Concurrency:: critical_section:: Lock](reference/critical-section-class.md#lock) yöntemi, zaten kilidin sahibi olan iş parçacığı tarafından çağrılırsa [concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) türünde bir özel durum oluşturur.

### <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda, sınıfı tarafından tanımlanan önemli Yöntemler gösterilmektedir `critical_section` .

|Yöntem|Açıklama|
|------------|-----------------|
|[ine](reference/critical-section-class.md#lock)|Kritik bölümü elde edin. Çağrıyı yapana kadar çağıran bağlam blokları.|
|[try_lock](reference/critical-section-class.md#try_lock)|Kritik bölümü almaya çalışır, ancak engellemez.|
|[kaldırın](reference/critical-section-class.md#unlock)|Kritik bölümünü yayınlar.|

[[Üst](#top)]

## <a name="reader_writer_lock"></a><a name="reader_writer_lock"></a>reader_writer_lock

[Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) sınıfı, paylaşılan verilere iş parçacığı açısından güvenli okuma/yazma işlemleri sağlar. Birden çok iş parçacığının paylaşılan bir kaynağa eşzamanlı okuma erişimi gerektirmesi ancak bu paylaşılan kaynağa nadiren yazmaları durumunda okuyucu/yazıcı kilitlerini kullanın. Bu sınıf, her zaman bir nesneye yalnızca bir iş parçacığı yazma erişimi sağlar.

`reader_writer_lock` `critical_section` Bir `critical_section` nesne, eşzamanlı okuma erişiminin önlediği paylaşılan bir kaynağa özel erişim elde ettiğinden sınıfı sınıftan daha iyi çalışabilir.

Sınıfı gibi `critical_section` , sınıfı, `reader_writer_lock` öncelik verme yerine diğer görevlere veren bir işbirlikçi karşılıklı dışlama nesnesini temsil eder.

Paylaşılan bir kaynağa yazılması gereken bir iş parçacığı okuyucu/yazıcı kilidi edindiğinde, yazıcıya erişmesi gereken diğer iş parçacıkları, yazıcı kilidi serbest bırakana kadar engellenir. Bu `reader_writer_lock` sınıf, bir *yazma tercihi* kilidinin bir örneğidir. Bu bir kilit, okuyucuları beklemeyi kaldırmadan önce, yazıcıların beklemeyi engeller.

Sınıfı gibi `critical_section` , sınıfı da yer `reader_writer_lock` yok. [Concurrency:: reader_writer_lock:: Lock](reference/reader-writer-lock-class.md#lock) ve [concurrency:: reader_writer_lock:: lock_read](reference/reader-writer-lock-class.md#lock_read) yöntemleri, `improper_lock` zaten kilidin sahibi olan bir iş parçacığı tarafından çağrıldıklarında türünde bir özel durum oluşturur.

> [!NOTE]
> Sınıf, bir `reader_writer_lock` salt okuma kilidini bir okuyucu/yazıcı kilidine yükseltemez veya bir okuyucu/yazıcı kilidini salt bir kilit ile indirgeyemezsiniz. Bu işlemlerden birini gerçekleştirmek, belirtilmeyen bir davranış üretir.

### <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda, sınıfı tarafından tanımlanan önemli Yöntemler gösterilmektedir `reader_writer_lock` .

|Yöntem|Açıklama|
|------------|-----------------|
|[ine](reference/reader-writer-lock-class.md#lock)|Kilit için okuma/yazma erişimi elde edin.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Kilit için okuma/yazma erişimi edinmeye çalışır, ancak engellemez.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Kilit için salt okuma erişimi sağlar.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Kilit için salt okunurdur erişim elde etmeye çalışır, ancak engellemez.|
|[kaldırın](reference/reader-writer-lock-class.md#unlock)|Kilidi serbest bırakır.|

[[Üst](#top)]

## <a name="scoped_lock-and-scoped_lock_read"></a><a name="scoped_lock"></a>scoped_lock ve scoped_lock_read

`critical_section`Ve `reader_writer_lock` sınıfları, karşılıklı dışlama nesneleriyle çalışma yöntemini basitleştiren iç içe geçmiş yardımcı sınıflar sağlar. Bu yardımcı sınıflar, *kapsamlı kilitler*olarak bilinir.

`critical_section`Sınıfı [concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) sınıfını içerir. Oluşturucu, belirtilen nesneye erişim sağlar `critical_section` ; yıkıcı bu nesneye erişimi yayınlar. `reader_writer_lock`Sınıfı, benzer [eşzamanlılık:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) sınıfını içerir, `critical_section::scoped_lock` bunun dışında, belirtilen nesneye yazma erişimini yönetmektedir `reader_writer_lock` . `reader_writer_lock`Sınıfı ayrıca [concurrency:: reader_writer_lock:: scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) sınıfını içerir. Bu sınıf, belirtilen nesneye okuma erişimini yönetir `reader_writer_lock` .

Kapsamlı kilitler, `critical_section` ve nesneleriyle el ile çalışırken çeşitli avantajlar sağlar `reader_writer_lock` . Genellikle, yığın üzerinde kapsamlı bir kilit ayırabilirsiniz. Kapsamlı bir kilit, yok edildiğinde karşılıklı dışlama nesnesine otomatik olarak erişim sağlar; Bu nedenle, temel alınan nesnenin kilidini el ile açamazsınız. Bu, bir işlev birden çok deyim içerdiğinde yararlıdır **`return`** . Kapsamlı kilitler Ayrıca özel durum güvenli kod yazmanıza yardımcı olabilir. Bir **`throw`** ifade yığının geriye doğru neden olduğunda, herhangi bir etkin kapsamlı kilit için yıkıcı çağrılır ve bu nedenle karşılıklı dışlama nesnesi her zaman doğru şekilde serbest bırakılır.

> [!NOTE]
> `critical_section::scoped_lock`, Ve sınıflarını kullandığınızda, `reader_writer_lock::scoped_lock` `reader_writer_lock::scoped_lock_read` temel karşılıklı dışlama nesnesine erişimi el ile serbest bırakmayın. Bu, çalışma zamanını geçersiz bir duruma yerleştirebilir.

## <a name="event"></a><a name="event"></a>olay

[Concurrency:: Event](../../parallel/concrt/reference/event-class.md) sınıfı, durumu sinyal veya sinyal olmayan bir eşitleme nesnesini temsil eder. Önemli bölümler gibi eşitleme nesnelerinin aksine, amacı paylaşılan verilere erişimi korumak için, olaylar yürütme akışını eşitler.

Sınıfı, bir `event` görev başka bir görev için çalışmayı tamamladığında yararlı olur. Örneğin, bir görev bir ağ bağlantısından veya bir dosyadan veri okuduğunuzu belirten başka bir göreve işaret edebilir.

### <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda, sınıfı tarafından tanımlanan önemli yöntemlerin birkaçı gösterilmektedir `event` .

|Yöntem|Açıklama|
|------------|-----------------|
|[bekleneceğini](reference/event-class.md#wait)|Olayın sinyal gelmesini bekler.|
|[kurmak](reference/event-class.md#set)|Olayı sinyal durumuna ayarlar.|
|[döndürmek](reference/event-class.md#reset)|Olayı, sinyal olmayan duruma ayarlar.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Birden çok olayın sinyal gelmesini bekler.|

### <a name="example"></a>Örnek

Sınıfının nasıl kullanılacağını gösteren bir örnek için `event` , bkz. [eşitleme veri YAPıLARıNı Windows API ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Üst](#top)]

## <a name="related-sections"></a>İlgili Bölümler

[Eşitleme veri yapılarını Windows API ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Eşitleme verileri yapılarının davranışını Windows API 'SI tarafından sağlananlarla karşılaştırır.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
Paralel programlamayı kolaylaştıran ve ilgili konuların bağlantılarını içeren Eşzamanlılık Çalışma Zamanı açıklar.

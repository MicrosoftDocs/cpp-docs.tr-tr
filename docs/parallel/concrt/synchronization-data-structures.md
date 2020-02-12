---
title: Eşitleme Veri Yapıları
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: 85dec6b003330a3560ae1dcc5c41b5e6d49f765e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142802"
---
# <a name="synchronization-data-structures"></a>Eşitleme Veri Yapıları

Eşzamanlılık Çalışma Zamanı, birden çok iş parçacığından paylaşılan verilere erişimi eşitlemenize olanak sağlayan çeşitli veri yapıları sağlar. Bu veri yapıları, seyrek olarak değiştirdiğiniz verileri paylaştığınız zaman yararlıdır. Bir eşitleme nesnesi, Örneğin kritik bir bölüm, diğer iş parçacıklarının paylaşılan kaynak kullanılabilir olana kadar beklemesini sağlar. Bu nedenle, sık kullanılan verilere erişimi eşleştirmek için böyle bir nesne kullanırsanız, uygulamanızda ölçeklenebilirliği kaybedebilirsiniz. [Paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) , eşitlemeye gerek olmadan bir kaynağı birçok iş parçacığı veya görev arasında paylaşmanızı sağlayan [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını sağlar. `combinable` sınıfı hakkında daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="top"></a>Başlıklı

Bu konuda, aşağıdaki zaman uyumsuz ileti bloğu türleri ayrıntılı olarak açıklanmaktadır:

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock ve scoped_lock_read](#scoped_lock)

- [event](#event)

## <a name="critical_section"></a>critical_section

[Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfı, öncelik verme yerine diğer görevlere veren bir işbirlikçi karşılıklı dışlama nesnesini temsil eder. Kritik bölümler, birden çok iş parçacığının paylaşılan verilere özel okuma ve yazma erişimi gerektirmesi durumunda faydalıdır.

`critical_section` sınıfı yer yok. [Concurrency:: critical_section:: Lock](reference/critical-section-class.md#lock) yöntemi, zaten kilidin sahibi olan iş parçacığı tarafından çağrılırsa [concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) türünde bir özel durum oluşturur.

### <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda `critical_section` sınıfı tarafından tanımlanan önemli Yöntemler gösterilmektedir.

|Yöntem|Açıklama|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|Kritik bölümü elde edin. Çağrıyı yapana kadar çağıran bağlam blokları.|
|[try_lock](reference/critical-section-class.md#try_lock)|Kritik bölümü almaya çalışır, ancak engellemez.|
|[kaldırın](reference/critical-section-class.md#unlock)|Kritik bölümünü yayınlar.|

[[Üst](#top)]

## <a name="reader_writer_lock"></a>reader_writer_lock

[Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) sınıfı, paylaşılan verilere iş parçacığı açısından güvenli okuma/yazma işlemleri sağlar. Birden çok iş parçacığının paylaşılan bir kaynağa eşzamanlı okuma erişimi gerektirmesi ancak bu paylaşılan kaynağa nadiren yazmaları durumunda okuyucu/yazıcı kilitlerini kullanın. Bu sınıf, her zaman bir nesneye yalnızca bir iş parçacığı yazma erişimi sağlar.

Bir `critical_section` nesnesi, eşzamanlı okuma erişimini önleyen bir paylaşılan kaynağa özel erişim elde ettiğinden, `reader_writer_lock` sınıfı `critical_section` sınıftan daha iyi çalışabilir.

`critical_section` sınıfı gibi `reader_writer_lock` sınıfı, öncelik verme yerine diğer görevlere veren bir işbirlikçi karşılıklı dışlama nesnesini temsil eder.

Paylaşılan bir kaynağa yazılması gereken bir iş parçacığı okuyucu/yazıcı kilidi edindiğinde, yazıcıya erişmesi gereken diğer iş parçacıkları, yazıcı kilidi serbest bırakana kadar engellenir. `reader_writer_lock` sınıfı, bir *yazma tercihi* kilidine örnektir. Bu bir kilit, okuyucuları beklemeyi kaldırmadan önce, yazıcıların beklemeyi engeller.

`critical_section` sınıfı gibi `reader_writer_lock` sınıfı da yer değildir. [Concurrency:: reader_writer_lock:: Lock](reference/reader-writer-lock-class.md#lock) ve [concurrency:: reader_writer_lock:: lock_read](reference/reader-writer-lock-class.md#lock_read) yöntemleri, zaten kilidin sahibi olan bir iş parçacığı tarafından çağrıldıklarında, `improper_lock` türünde bir özel durum oluşturur.

> [!NOTE]
> `reader_writer_lock` sınıfı yer lamadığından, bir okuyucu/yazıcı kilidine salt okunurdur veya bir okuyucu/yazıcı kilidini salt bir kilit için indirgeyemezsiniz. Bu işlemlerden birini gerçekleştirmek, belirtilmeyen bir davranış üretir.

### <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda `reader_writer_lock` sınıfı tarafından tanımlanan önemli Yöntemler gösterilmektedir.

|Yöntem|Açıklama|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|Kilit için okuma/yazma erişimi elde edin.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Kilit için okuma/yazma erişimi edinmeye çalışır, ancak engellemez.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Kilit için salt okuma erişimi sağlar.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Kilit için salt okunurdur erişim elde etmeye çalışır, ancak engellemez.|
|[kaldırın](reference/reader-writer-lock-class.md#unlock)|Kilidi serbest bırakır.|

[[Üst](#top)]

## <a name="scoped_lock"></a>scoped_lock ve scoped_lock_read

`critical_section` ve `reader_writer_lock` sınıfları, karşılıklı dışlama nesneleriyle çalışma yöntemini basitleştiren iç içe geçmiş yardımcı sınıflar sağlar. Bu yardımcı sınıflar, *kapsamlı kilitler*olarak bilinir.

`critical_section` sınıfı [concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) sınıfını içerir. Oluşturucu, belirtilen `critical_section` nesnesine erişim sağlar; yıkıcı bu nesneye erişimi serbest bırakır. `reader_writer_lock` sınıfı, sunulan `reader_writer_lock` nesnesine yazma erişimini yönetmesi dışında, `critical_section::scoped_lock`benzeyen [concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) sınıfını içerir. `reader_writer_lock` sınıfı [concurrency:: reader_writer_lock:: scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) sınıfını da içerir. Bu sınıf, belirtilen `reader_writer_lock` nesnesine okuma erişimini yönetir.

Kapsamlı kilitler `critical_section` `reader_writer_lock` ve nesneleriyle el ile çalışırken çeşitli avantajlar sağlar. Genellikle, yığın üzerinde kapsamlı bir kilit ayırabilirsiniz. Kapsamlı bir kilit, yok edildiğinde karşılıklı dışlama nesnesine otomatik olarak erişim sağlar; Bu nedenle, temel alınan nesnenin kilidini el ile açamazsınız. Bu, bir işlev birden çok `return` deyimi içerdiğinde yararlıdır. Kapsamlı kilitler Ayrıca özel durum güvenli kod yazmanıza yardımcı olabilir. `throw` bir ifade, yığının Geriye kaydedilmesine neden olduğunda, herhangi bir etkin kapsamlı kilit için yıkıcı çağrılır ve bu nedenle karşılıklı dışlama nesnesi her zaman doğru şekilde serbest bırakılır.

> [!NOTE]
> `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`ve `reader_writer_lock::scoped_lock_read` sınıflarını kullandığınızda, temel karşılıklı dışlama nesnesine erişimi el ile serbest bırakmayın. Bu, çalışma zamanını geçersiz bir duruma yerleştirebilir.

## <a name="event"></a>olay

[Concurrency:: Event](../../parallel/concrt/reference/event-class.md) sınıfı, durumu sinyal veya sinyal olmayan bir eşitleme nesnesini temsil eder. Önemli bölümler gibi eşitleme nesnelerinin aksine, amacı paylaşılan verilere erişimi korumak için, olaylar yürütme akışını eşitler.

`event` sınıfı, bir görev başka bir görev için çalışmayı tamamladığında yararlı olur. Örneğin, bir görev bir ağ bağlantısından veya bir dosyadan veri okuduğunuzu belirten başka bir göreve işaret edebilir.

### <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda `event` sınıfı tarafından tanımlanan önemli yöntemlerin bazıları gösterilmektedir.

|Yöntem|Açıklama|
|------------|-----------------|
|[bekleneceğini](reference/event-class.md#wait)|Olayın sinyal gelmesini bekler.|
|[set](reference/event-class.md#set)|Olayı sinyal durumuna ayarlar.|
|[döndürmek](reference/event-class.md#reset)|Olayı, sinyal olmayan duruma ayarlar.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Birden çok olayın sinyal gelmesini bekler.|

### <a name="example"></a>Örnek

`event` sınıfının nasıl kullanılacağını gösteren bir örnek için, bkz. [eşitleme veri yapılarını WINDOWS API Ile karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).

[[Üst](#top)]

## <a name="related-sections"></a>İlgili Bölümler

[Eşitleme Veri Yapılarını Windows API ile Karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Eşitleme verileri yapılarının davranışını Windows API 'SI tarafından sağlananlarla karşılaştırır.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
Paralel programlamayı kolaylaştıran ve ilgili konuların bağlantılarını içeren Eşzamanlılık Çalışma Zamanı açıklar.

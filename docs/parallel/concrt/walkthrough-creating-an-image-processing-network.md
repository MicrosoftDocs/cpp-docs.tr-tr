---
title: 'İzlenecek yol: Görüntü İşleme Ağı Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 4eb1d6f9e5bc0055a1a4b4be5e18497b20c3a73a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643644"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>İzlenecek yol: Görüntü İşleme Ağı Oluşturma

Bu belge ağ görüntü işleme gerçekleştiren zaman uyumsuz ileti blokları oluşturma işlemini gösterir.

Ağ özelliklerini temel alarak bir görüntüye gerçekleştirilecek işlemleri belirler. Bu örnekte *veri akışı* rota görüntülerini ağ üzerinden için model. Veri akışı modelinde, bir program bağımsız bileşenleri birbirleriyle iletiler göndererek iletişim. Bir bileşenin bir ileti aldığında, bu bazı eylemler gerçekleştirme ve ardından bu eylemin sonucu başka bir bileşene geçirin. Şununla Karşılaştır *denetim akışı* modelini, uygulamanın kullandığı denetim yapıları, örneğin, koşullu deyimler, döngüler ve benzeri işlemlerin bir programda sırasını denetlemek için.

Veri akışı üzerinde temel bir ağ oluşturur bir *işlem hattı* görev. Ardışık düzenin her aşaması, eşzamanlı olarak genel görevinin bir parçası yapar. Bu bir benzerliği otomobil üretimde montaj ' dir. Her araç montaj hattı geçerken çerçevenin bir istasyondan birleştirir, başka altyapısı ve benzeri yükler. Aynı anda birleştirilmeleri birden çok Araçlar sağlayarak montaj hattı tam araçları bir anda derleyerek daha iyi aktarım hızı sağlar.

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Temel GDI +'da bu kılavuza başlamadan önce anlamanız da öneririz.

##  <a name="top"></a> Bölümleri

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Görüntü işleme işlevleri tanımlama](#functionality)

- [Görüntü işleme ağı oluşturma](#network)

- [Tam örnek](#complete)

##  <a name="functionality"></a> Görüntü işleme işlevleri tanımlama

Bu bölüm, görüntü işleme ağı diskten okunan görüntüleri çalışmak için kullandığı destek işlevlerini gösterir.

Aşağıdaki işlevleri `GetRGB` ve `MakeColor`, ayıklayın ve belirli renk bileşenleri tek tek sırasıyla birleştirin.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Aşağıdaki işlev `ProcessImage`, çağrıları verilen [std::function](../../standard-library/function-class.md) GDI +'daki her piksel renk değerini dönüştürmek için nesne [bit eşlem](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesne. `ProcessImage` İşlevini kullanan [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını paralel bit eşlemin her satır işlenecek.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

Aşağıdaki işlevleri `Grayscale`, `Sepiatone`, `ColorMask`, ve `Darken`, çağrı `ProcessImage` her piksel renk değerini dönüştürmek için işlevi bir `Bitmap` nesne. Bu işlevlerin her biri bir piksel renk dönüştürülmesini tanımlamak için bir lambda ifadesi kullanır.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Aşağıdaki işlev `GetColorDominance`, ayrıca çağırır `ProcessImage` işlevi. Ancak, bu işlev her renk değerinin değiştirilmesi yerine kullanır [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) kırmızı, yeşil ve mavi renk bileşeni görüntü kaplamaktadır olmadığını hesaplamak için nesne.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Aşağıdaki işlev `GetEncoderClsid`, sınıf tanımlayıcısı bir kodlayıcı belirtilen MIME türünü alır. Uygulama için bir bit eşlem Kodlayıcı almak için bu işlevi kullanır.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[Üst](#top)]

##  <a name="network"></a> Görüntü işleme ağı oluşturma

Bu bölümde belirli bir dizinin her JPEG (.jpg) görüntüye görüntü işleme gerçekleştiren zaman uyumsuz ileti blokları ağı oluşturmayı açıklar. Ağ aşağıdaki görüntü işleme işlemleri gerçekleştirir:

1. Tom tarafından yazılan herhangi bir görüntü için gri tonlamaya dönüştürme.

1. Baskın renk olarak kırmızı sahip herhangi bir görüntü için yeşil ve mavi bileşenlerinin kaldırın ve sonra koyu.

1. Sepya tonlama başka herhangi bir görüntü için geçerlidir.

Ağ, Bu koşullardan biri eşleşen yalnızca ilk görüntü işleme işlemi uygular. Örneğin, bir görüntü Tom tarafından yazılan ve baskın rengini kırmızı varsa, görüntünün yalnızca gri tonlamaya dönüştürülür.

Ağ her görüntü işleme işlemi gerçekleştirdikten sonra görüntüyü bir bit eşlem (.bmp) dosyası olarak diske kaydeder.

Aşağıdaki adımlar, bu görüntü ağ işleme uygular ve her bir JPEG görüntüsünü belirli bir dizinde söz konusu ağ uygulandığı bir işlev oluşturma işlemi gösterilmektedir.

#### <a name="to-create-the-image-processing-network"></a>Görüntü işleme ağı oluşturma

1. Bir işlev oluşturma `ProcessImages`, disk üzerinde bir dizinin adını alır.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. İçinde `ProcessImages` işlev, oluşturun bir `countdown_event` değişkeni. `countdown_event` Sınıfı bu yönergelerin ilerleyen bölümünde gösterilir.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Oluşturma bir [std::map](../../standard-library/map-class.md) ilişkilendirir nesne bir `Bitmap` özgün dosya adıyla nesne.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Görüntü işleme ağı üyelerini tanımlamak için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Ağa bağlanmak için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Ağ başı her JPEG dosyasının tam yolu dizinde göndermek için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. Bekle `countdown_event` değişkeni sıfır ulaşmak için.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

Aşağıdaki tabloda, ağ üyelerini açıklar.

|Üye|Açıklama|
|------------|-----------------|
|`load_bitmap`|A [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) yükler nesne bir `Bitmap` diskten nesnesi ve bir girişi ekler `map` görüntünün özgün dosya adıyla ilişkilendirmek için nesne.|
|`loaded_bitmaps`|A [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) yüklenen görüntü için görüntü işleme filtreleri gönderen nesne.|
|`grayscale`|A `transformer` nesnesini gri tonlamaya Tom tarafından yazılmış iş görüntüleri dönüştürür. Görüntü meta verilerini yazarı belirlemek için kullanır.|
|`colormask`|A `transformer` nesnesini kırmızı olarak baskın renge sahip görüntüleri yeşil ve mavi renk bileşenlerine kaldırır.|
|`darken`|A `transformer` kırmızı olarak baskın renge sahip görüntüleri koyulaştırır nesne.|
|`sepiatone`|A `transformer` sepya tonlama Tom tarafından yazılan değil ve genellikle kırmızı olmayan görüntüleri için geçerli bir nesne.|
|`save_bitmap`|A `transformer` işlenen kaydeder nesne `image` diske bir bit eşlem olarak. `save_bitmap` Özgün dosya adını alır. `map` nesne ve .bmp için dosya adı uzantısını değiştirir.|
|`delete_bitmap`|A `transformer` görüntüleri için bellek serbest bırakan bir nesne.|
|`decrement`|A [concurrency::call](../../parallel/concrt/reference/call-class.md) ağ terminal düğümün gören nesne. Bunu azaltır `countdown_event` ana uygulama görüntü işlendiğini göstermek için nesne.|

`loaded_bitmaps` İleti arabelleği önemlidir çünkü, olarak bir `unbounded_buffer` nesne, sunduğu `Bitmap` birden çok alıcı nesneleri. Ne zaman bir hedef bloğu kabul eden bir `Bitmap` nesnesi `unbounded_buffer` nesne, sunmaz `Bitmap` nesneyi diğer tüm hedeflerden. Bu nedenle, bir bağlantı sırası nesneleri için bir `unbounded_buffer` nesne önemlidir. `grayscale`, `colormask`, Ve `sepiatone` ileti blokları her kabul etmek için bir filtre kullanan yalnızca belirli `Bitmap` nesneleri. `decrement` İleti arabelleği önemli bir hedefi olan `loaded_bitmaps` tüm kabul ettiğinden ileti arabelleği `Bitmap` diğer ileti arabelleklerinin tarafından reddedilen nesneleri. Bir `unbounded_buffer` nesnesinin sırasındaki iletilere yaymak için gereklidir. Bu nedenle, bir `unbounded_buffer` nesne, yeni bir hedef blok ona bağlı ve geçerli bir hedef blok bu iletiyi kabul ediyorsa, iletiyi kabul kadar engeller.

Uygulamanızı birden çok ileti işlemi yalnızca ilk iletiyi kabul bir ileti bloğu yerine ileti engeller gerektiriyorsa, başka bir mesaj engelleme türü gibi kullanabilirsiniz `overwrite_buffer`. `overwrite_buffer` Sınıf, bir kerede tek bir ileti içerir, ancak hedeflerinin her biri için bu iletiyi yayar.

Görüntü işleme ağı aşağıda gösterilmiştir:

![Görüntü işleme ağı](../../parallel/concrt/media/concrt_imageproc.png "concrt_imageproc")

`countdown_event` Nesnesi bu örnekte, tüm görüntüleri işlendiğinde ana uygulama bildirmek görüntü işleme ağı sağlar. `countdown_event` Sınıfını kullanan bir [concurrency::event](../../parallel/concrt/reference/event-class.md) sayaç değeri sıfır ulaştığında göstermek için nesne. BT'nin, ağ dosya adı gönderir her zaman ana uygulama sayaç artırılır. Ağ azaltır düzenin terminal düğümünden her görüntü işlendikten sonra sayacı. Belirtilen dizin ana uygulama eriştikten sonra bekler `countdown_event` kendi sayaç sıfır ulaştı göstermek için nesne.

Aşağıdaki örnekte gösterildiği `countdown_event` sınıfı:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[Üst](#top)]

##  <a name="complete"></a> Tam örnek

Aşağıdaki kod, tam bir örnek gösterir. `wmain` İşlevi yönetir GDI +'KİTAPLIĞI ve çağrıları `ProcessImages` JPEG işlenecek işlevi dosyaları `Sample Pictures` dizin.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

Örnek çıktı aşağıda gösterilmiştir. Her kaynak görüntüsü, karşılık gelen değiştirilmiş görüntüsüdür.

![Örnek çıktı örneğin](../../parallel/concrt/media/concrt_imageout.png "concrt_imageout")

`Lighthouse` Tom Alphin tarafından yazılan ve bu nedenle gri tonlamaya dönüştürülür. `Chrysanthemum`, `Desert`, `Koala`, ve `Tulips` baskın renk olarak kırmızı varsa ve bu nedenle kaldırıldı mavi ve yeşil renk bileşenlerine sahip ve koyu. `Hydrangeas`, `Jellyfish`, ve `Penguins` varsayılan ölçütlerle eşleşen ve bu nedenle toned sepya.

[[Üst](#top)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `image-processing-network.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe /DUNICODE/ehsc görüntü işleme network.cpp/Link gdiplus.lib**

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

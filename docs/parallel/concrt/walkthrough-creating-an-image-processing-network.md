---
title: 'İzlenecek yol: Görüntü İşleme Ağı Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 03d95be8fae3565a51811357ed9553c3a2649674
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140763"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>İzlenecek yol: Görüntü İşleme Ağı Oluşturma

Bu belge, görüntü işlemeyi gerçekleştiren zaman uyumsuz ileti bloklarının bir ağını oluşturmayı gösterir.

Ağ, bir görüntüde hangi işlemlerin özelliklerine göre gerçekleştirileceğini belirler. Bu örnek, görüntüleri ağ üzerinden yönlendirmek için *veri akışı* modelini kullanır. Veri akışı modelinde, bir programın bağımsız bileşenleri ileti göndererek birbirleriyle iletişim kurar. Bir bileşen bir ileti aldığında, bazı işlemleri gerçekleştirebilir ve sonra bu eylemin sonucunu başka bir bileşene geçirebilir. Bunu, bir uygulamanın bir programdaki işlem sırasını denetlemek için denetim yapılarını (örneğin, koşullu deyimler, döngüler vb.) kullandığı *Denetim akışı* modeliyle karşılaştırın.

Veri akışına dayalı bir ağ, görev *hattı* oluşturur. İşlem hattının her aşaması, genel görevin bir kısmını eşzamanlı olarak gerçekleştirir. Buna bir benzerleme vurguladı, otomobil üretimi için bir derleme satırdır. Her araç derleme satırından geçtiğinde, bir istasyon çerçeveyi ayrıştırır, başka bir altyapıyı de yüklerse ve bu şekilde devam eder. Birden çok taşıtın aynı anda derlenmelerini etkinleştirerek, derleme satırı, her seferinde bir tane olmak üzere, tamamlanmış bir şekilde bir araya getirilen daha iyi

## <a name="prerequisites"></a>Prerequisites

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Ayrıca, bu yönergeyi başlamadan önce GDI+ temel bilgilerini anlamanız önerilir.

## <a name="top"></a>Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Görüntü Işleme Işlevini tanımlama](#functionality)

- [Görüntü Işleme ağı oluşturuluyor](#network)

- [Tüm örnek](#complete)

## <a name="functionality"></a>Görüntü Işleme Işlevini tanımlama

Bu bölümde görüntü işleme ağının diskten okunan görüntülerle çalışmak için kullandığı destek işlevleri gösterilmektedir.

Aşağıdaki işlevler, `GetRGB` ve `MakeColor`, sırasıyla verilen rengin tek tek bileşenlerini ayıklar ve birleştirir.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Aşağıdaki işlev `ProcessImage`, bir GDI+ [bit eşlem](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesnesindeki her bir pikselin renk değerini dönüştürmek için verilen [std:: Function](../../standard-library/function-class.md) nesnesini çağırır. `ProcessImage` işlevi, bit eşlemin her satırını paralel olarak işlemek için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

Aşağıdaki işlevler, `Grayscale`, `Sepiatone`, `ColorMask`ve `Darken``ProcessImage` nesnedeki her pikselin renk değerini dönüştürmek için `Bitmap` işlevini çağırır. Bu işlevlerin her biri, bir pikselin renk dönüşümünü tanımlamak için bir lambda ifadesi kullanır.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Aşağıdaki işlev, `GetColorDominance``ProcessImage` işlevini de çağırır. Ancak, her rengin değerini değiştirmek yerine bu işlev, kırmızı, yeşil veya mavi renkli bileşenin görüntüyü kullanıp kullanmadığını hesaplamak için [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) nesnelerini kullanır.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Aşağıdaki işlev `GetEncoderClsid`, bir kodlayıcının verilen MIME türü için sınıf tanımlayıcısını alır. Uygulama, bir bit eşlem için kodlayıcıyı almak üzere bu işlevi kullanır.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[Üst](#top)]

## <a name="network"></a>Görüntü Işleme ağı oluşturuluyor

Bu bölümde, belirli bir dizindeki her JPEG (. jpg) görüntüsünde görüntü işleme yapan bir zaman uyumsuz ileti blokları ağı oluşturma işlemi açıklanmaktadır. Ağ aşağıdaki görüntü işleme işlemlerini gerçekleştirir:

1. Tom tarafından yazılan herhangi bir görüntü için gri tonlamaya dönüştürün.

1. Baskın renk olarak kırmızı olan herhangi bir görüntü için yeşil ve mavi bileşenleri kaldırın ve ardından bunu koyulaştırın.

1. Diğer herhangi bir görüntü için sepıa tonlama ' yı uygulayın.

Ağ yalnızca bu koşullardan biriyle eşleşen ilk görüntü işleme işlemini uygular. Örneğin, bir görüntü Tom tarafından yazılmışsa ve baskın rengi olarak kırmızıysa, görüntü yalnızca gri tonlamaya dönüştürülür.

Ağ her görüntü işleme işlemini gerçekleştirdikten sonra görüntüyü diske bir bit eşlem (. bmp) dosyası olarak kaydeder.

Aşağıdaki adımlarda, bu görüntü işleme ağını uygulayan ve bu ağı belirli bir dizindeki her JPEG görüntüsüne uygulayan bir işlevin nasıl oluşturulacağı gösterilmektedir.

#### <a name="to-create-the-image-processing-network"></a>Görüntü işleme ağını oluşturmak için

1. Diskteki bir dizinin adını alan `ProcessImages`bir işlev oluşturun.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. `ProcessImages` işlevinde, bir `countdown_event` değişkeni oluşturun. `countdown_event` sınıfı Bu izlenecek yolun ilerleyen kısımlarında gösterilmektedir.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. `Bitmap` nesnesini özgün dosya adıyla ilişkilendiren [std:: Map](../../standard-library/map-class.md) nesnesi oluşturun.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Görüntü işleme ağının üyelerini tanımlamak için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Ağı bağlamak için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Dizindeki her bir JPEG dosyasının tam yolunu ağa göndermek için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. `countdown_event` değişkeninin sıfıra ulaşmasını bekleyin.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

Aşağıdaki tablo, ağın üyelerini açıklar.

|Üye|Açıklama|
|------------|-----------------|
|`load_bitmap`|Diskten bir `Bitmap` nesnesi yükleyen ve `map` nesnesine bir girdi ekleyen bir [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) nesnesi, resmi özgün dosya adıyla ilişkilendirmenizi sağlar.|
|`loaded_bitmaps`|Görüntü işleme filtrelerine yüklenen görüntüleri gönderen bir [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi.|
|`grayscale`|Tom tarafından yazılan görüntüleri gri tonlamalı olarak dönüştüren `transformer` nesnesi. Onun yazarını öğrenmek için görüntünün meta verilerini kullanır.|
|`colormask`|Baskın renk olarak kırmızı olan görüntülerden yeşil ve mavi renkli bileşenleri kaldıran `transformer` nesnesi.|
|`darken`|Baskın renk olarak kırmızı olan görüntüleri koyulaştırır `transformer` nesne.|
|`sepiatone`|Tom tarafından yazılmamış ve ağırlıklı Red olmayan görüntülere sepıa tonlama uygulayan `transformer` nesne.|
|`save_bitmap`|İşlenen `image` diske bir bit eşlem olarak kaydeden `transformer` nesnesi. `save_bitmap`, `map` nesnesinden özgün dosya adını alır ve dosya adı uzantısını. bmp olarak değiştirir.|
|`delete_bitmap`|Görüntüler için belleği serbest bıraktığı bir `transformer` nesnesi.|
|`decrement`|Ağda Terminal düğümü görevi gören bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesi. `countdown_event` nesnesini, bir görüntünün işlendiği ana uygulamaya işaret etmek üzere azaltır.|

`loaded_bitmaps` ileti arabelleği önemlidir çünkü bu, `unbounded_buffer` bir nesne olarak birden çok alıcıya `Bitmap` nesneleri sunmaktadır. Bir hedef blok bir `Bitmap` nesnesini kabul ettiğinde, `unbounded_buffer` nesnesi bu `Bitmap` nesnesini diğer hedeflere sunmaz. Bu nedenle, nesneleri bir `unbounded_buffer` nesnesine bağlama sırası önemlidir. `grayscale`, `colormask`ve `sepiatone` ileti blokları, yalnızca belirli `Bitmap` nesnelerini kabul etmek için bir filtre kullanır. `decrement` ileti arabelleği, diğer ileti arabelleklerinin reddettiği tüm `Bitmap` nesnelerini kabul ettiğinden `loaded_bitmaps` ileti arabelleğinin önemli bir hedefidir. İletileri sırayla yaymak için bir `unbounded_buffer` nesnesi gerekir. Bu nedenle, bir `unbounded_buffer` nesnesi yeni hedef bloğunun bağlanana kadar engeller ve geçerli hedef bloğu bu iletiyi kabul ettiyse iletiyi kabul eder.

Uygulamanız birden çok ileti bloğunun iletiyi işlemesini gerektiriyorsa, yalnızca iletiyi kabul eden bir ileti bloğu yerine, `overwrite_buffer`gibi başka bir ileti bloğu türü kullanabilirsiniz. `overwrite_buffer` sınıfı tek seferde bir ileti barındırır, ancak bu iletiyi her bir hedefe yayar.

Aşağıdaki çizim görüntü işleme ağını göstermektedir:

![Görüntü işleme ağı](../../parallel/concrt/media/concrt_imageproc.png "Görüntü işleme ağı")

Bu örnekteki `countdown_event` nesnesi, görüntü işleme ağının tüm görüntüler işlendiğinde ana uygulamayı bilgilendirmesini sağlar. `countdown_event` sınıfı, bir sayaç değeri sıfıra ulaştığında sinyal almak için bir [concurrency:: Event](../../parallel/concrt/reference/event-class.md) nesnesi kullanır. Ana uygulama, her bir dosya adını ağa gönderdiğinde sayacı artırır. Ağın Terminal düğümü, her görüntü işlendikten sonra sayacı azaltır. Ana uygulama belirtilen dizinden geçtikten sonra, `countdown_event` nesnenin sayacın sıfıra ulaşmış olduğunu işaret etmek için bekler.

Aşağıdaki örnekte `countdown_event` sınıfı gösterilmektedir:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[Üst](#top)]

## <a name="complete"></a>Tüm örnek

Aşağıdaki kod, tüm örneği göstermektedir. `wmain` işlevi, GDI+ kitaplığını yönetir ve `Sample Pictures` dizinindeki JPEG dosyalarını işlemek için `ProcessImages` işlevini çağırır.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

Aşağıdaki çizimde örnek çıkış gösterilmektedir. Her kaynak görüntü, kendisine karşılık gelen değiştirilmiş görüntünün üzerinde.

![Örnek için örnek çıktı](../../parallel/concrt/media/concrt_imageout.png "Örnek için örnek çıktı")

`Lighthouse` Tom Alphin tarafından yazılır ve bu nedenle gri tonlamaya dönüştürülür. `Chrysanthemum`, `Desert`, `Koala`ve `Tulips`, baskın renk olarak kırmızı ve bu nedenle mavi ve yeşil renkli bileşenleri kaldırılmış ve koyulaştırılan. `Hydrangeas`, `Jellyfish`ve `Penguins` Varsayılan ölçütlere göre eşleşir ve bu nedenle, yarı PIA alınır.

[[Üst](#top)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `image-processing-network.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

**CL. exe/DUNıCODE/EHsc image-Processing-Network. cpp/link Gdiplus. lib**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

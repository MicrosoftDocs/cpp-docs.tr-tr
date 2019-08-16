---
title: 'İzlenecek yol: Görüntü Işleme ağı oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 680037e0e14c3ebd9171cacf477520e025eecebe
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512168"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>İzlenecek yol: Görüntü Işleme ağı oluşturma

Bu belge, görüntü işlemeyi gerçekleştiren zaman uyumsuz ileti bloklarının bir ağını oluşturmayı gösterir.

Ağ, bir görüntüde hangi işlemlerin özelliklerine göre gerçekleştirileceğini belirler. Bu örnek, görüntüleri ağ üzerinden yönlendirmek için *veri akışı* modelini kullanır. Veri akışı modelinde, bir programın bağımsız bileşenleri ileti göndererek birbirleriyle iletişim kurar. Bir bileşen bir ileti aldığında, bazı işlemleri gerçekleştirebilir ve sonra bu eylemin sonucunu başka bir bileşene geçirebilir. Bunu, bir uygulamanın bir programdaki işlem sırasını denetlemek için denetim yapılarını (örneğin, koşullu deyimler, döngüler vb.) kullandığı *Denetim akışı* modeliyle karşılaştırın.

Veri akışına dayalı bir ağ, görev *hattı* oluşturur. İşlem hattının her aşaması, genel görevin bir kısmını eşzamanlı olarak gerçekleştirir. Buna bir benzerleme vurguladı, otomobil üretimi için bir derleme satırdır. Her araç derleme satırından geçtiğinde, bir istasyon çerçeveyi ayrıştırır, başka bir altyapıyı de yüklerse ve bu şekilde devam eder. Birden çok taşıtın aynı anda derlenmelerini etkinleştirerek, derleme satırı, her seferinde bir tane olmak üzere, tamamlanmış bir şekilde bir araya getirilen daha iyi

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [İzlenecek yol: Veri Akış Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Ayrıca, bu yönergeyi başlamadan önce GDI+ temel bilgilerini anlamanız önerilir.

##  <a name="top"></a>Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Görüntü Işleme Işlevini tanımlama](#functionality)

- [Görüntü Işleme ağı oluşturuluyor](#network)

- [Tüm örnek](#complete)

##  <a name="functionality"></a>Görüntü Işleme Işlevini tanımlama

Bu bölümde görüntü işleme ağının diskten okunan görüntülerle çalışmak için kullandığı destek işlevleri gösterilmektedir.

Aşağıdaki işlevleri, `GetRGB` ve `MakeColor`sırasıyla verilen rengin tek tek bileşenlerini ayıklar ve birleştirir.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Aşağıdaki işlev `ProcessImage`, bir GDI+ [bit eşlem](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) nesnesindeki her bir pikselin renk değerini dönüştürmek için verilen [std:: Function](../../standard-library/function-class.md) nesnesini çağırır. İşlevi, bit eşlemin her satırını paralel olarak işlemek için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır. `ProcessImage`

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

`Grayscale`Aşağıdaki işlevleri, `Sepiatone` `ProcessImage` ,, `Bitmap` ve `Darken`, bir nesnedeki her bir pikselin renk değerini dönüştürmek için işlevini çağırır. `ColorMask` Bu işlevlerin her biri, bir pikselin renk dönüşümünü tanımlamak için bir lambda ifadesi kullanır.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Aşağıdaki işlev `GetColorDominance`, `ProcessImage` işlevini de çağırır. Ancak, her rengin değerini değiştirmek yerine bu işlev, kırmızı, yeşil veya mavi renkli bileşenin görüntüyü kullanıp kullanmadığını hesaplamak için [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) nesnelerini kullanır.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Aşağıdaki işlev `GetEncoderClsid`, bir kodlayıcı için verilen MIME türü için sınıf tanımlayıcısını alır. Uygulama, bir bit eşlem için kodlayıcıyı almak üzere bu işlevi kullanır.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[Üst](#top)]

##  <a name="network"></a>Görüntü Işleme ağı oluşturuluyor

Bu bölümde, belirli bir dizindeki her JPEG (. jpg) görüntüsünde görüntü işleme yapan bir zaman uyumsuz ileti blokları ağı oluşturma işlemi açıklanmaktadır. Ağ aşağıdaki görüntü işleme işlemlerini gerçekleştirir:

1. Tom tarafından yazılan herhangi bir görüntü için gri tonlamaya dönüştürün.

1. Baskın renk olarak kırmızı olan herhangi bir görüntü için yeşil ve mavi bileşenleri kaldırın ve ardından bunu koyulaştırın.

1. Diğer herhangi bir görüntü için sepıa tonlama ' yı uygulayın.

Ağ yalnızca bu koşullardan biriyle eşleşen ilk görüntü işleme işlemini uygular. Örneğin, bir görüntü Tom tarafından yazılmışsa ve baskın rengi olarak kırmızıysa, görüntü yalnızca gri tonlamaya dönüştürülür.

Ağ her görüntü işleme işlemini gerçekleştirdikten sonra görüntüyü diske bir bit eşlem (. bmp) dosyası olarak kaydeder.

Aşağıdaki adımlarda, bu görüntü işleme ağını uygulayan ve bu ağı belirli bir dizindeki her JPEG görüntüsüne uygulayan bir işlevin nasıl oluşturulacağı gösterilmektedir.

#### <a name="to-create-the-image-processing-network"></a>Görüntü işleme ağını oluşturmak için

1. Diskteki bir dizinin adını `ProcessImages`alan bir işlev oluşturun.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. `ProcessImages` İşlevinde bir`countdown_event` değişken oluşturun. `countdown_event` Sınıfı Bu izlenecek yolda daha sonra gösterilmiştir.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Bir`Bitmap` nesneyi özgün dosya adıyla ilişkilendiren [std:: Map](../../standard-library/map-class.md) nesnesi oluşturun.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Görüntü işleme ağının üyelerini tanımlamak için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Ağı bağlamak için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Dizindeki her bir JPEG dosyasının tam yolunu ağa göndermek için aşağıdaki kodu ekleyin.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. `countdown_event` Değişkenin sıfıra ulaşmasını bekleyin.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

Aşağıdaki tablo, ağın üyelerini açıklar.

|Üye|Açıklama|
|------------|-----------------|
|`load_bitmap`|Diskten bir `Bitmap` nesne yükleyen ve resmi özgün dosya adıyla ilişkilendirmek için `map` nesnesine bir giriş ekleyen bir [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) nesnesi.|
|`loaded_bitmaps`|Görüntü işleme filtrelerine yüklenen görüntüleri gönderen bir [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi.|
|`grayscale`|Tom `transformer` tarafından yazılan görüntüleri gri tonlamalı olarak dönüştüren bir nesne. Onun yazarını öğrenmek için görüntünün meta verilerini kullanır.|
|`colormask`|Baskın `transformer` renk olarak kırmızı olan görüntülerden yeşil ve mavi renkli bileşenleri kaldıran bir nesne.|
|`darken`|Baskın renk olarak kırmızı olan görüntüleri koyulaştırır nesne.`transformer`|
|`sepiatone`|Tom `transformer` tarafından yazılmayan ve ağırlıklı Red olmayan görüntülere sepıa için bir resim uygulayan nesne.|
|`save_bitmap`|`transformer` İşlenen`image` öğesini diske bit eşlem olarak kaydeden bir nesne. `save_bitmap``map` nesnesinden özgün dosya adını alır ve dosya adı uzantısını. bmp olarak değiştirir.|
|`delete_bitmap`|Görüntüler `transformer` için belleği serbest bıraktığı bir nesne.|
|`decrement`|Ağda Terminal düğümü görevi gören bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesi. Bir görüntünün işlendiği ana `countdown_event` uygulamaya işaret etmek için nesneyi azaltır.|

`Bitmap` Bir `loaded_bitmaps` nesneolarakbirdençokalıcıya`unbounded_buffer` nesne sunduğundan, ileti arabelleği önemlidir. Bir hedef blok bir `Bitmap` nesneyi kabul ettiğinde `unbounded_buffer` , nesne bu `Bitmap` nesneyi başka hiçbir hedefe sunmaz. Bu nedenle, nesneleri bir `unbounded_buffer` nesneye bağlamak için önemli olan sıra önemlidir. ,, Ve `Bitmap` ileti blokları, yalnızca belirli nesneleri kabul etmek için bir filtre kullanır. `sepiatone` `colormask` `grayscale` İleti arabelleği, diğer ileti arabellekleri tarafından reddedilen tüm `loaded_bitmaps` `Bitmap` nesneleri kabul ettiğinden ileti arabelleğinin önemli bir hedefidir. `decrement` İletileri `unbounded_buffer` sırayla yaymak için bir nesne gerekir. Bu nedenle, `unbounded_buffer` bir nesne yeni bir hedef bloğuna bağlanana kadar engeller ve geçerli hedef bloğu bu iletiyi kabul ettiyse iletiyi kabul eder.

Uygulamanız birden çok ileti bloğunun iletiyi işlemesini gerektiriyorsa, yalnızca iletiyi kabul eden bir ileti bloğu yerine, gibi `overwrite_buffer`başka bir ileti bloğu türü kullanabilirsiniz. `overwrite_buffer` Sınıf tek seferde bir ileti tutar, ancak bu iletiyi her bir hedefine yayar.

Aşağıdaki çizim görüntü işleme ağını göstermektedir:

![Görüntü işleme ağı](../../parallel/concrt/media/concrt_imageproc.png "Görüntü işleme ağı")

Bu `countdown_event` örnekteki nesne, görüntü işleme ağının tüm görüntüler işlendiğinde ana uygulamayı bilgilendirmesini sağlar. Sınıfı `countdown_event` , bir sayaç değeri sıfıra ulaştığında işaret etmek için bir [concurrency:: Event](../../parallel/concrt/reference/event-class.md) nesnesi kullanır. Ana uygulama, her bir dosya adını ağa gönderdiğinde sayacı artırır. Ağın Terminal düğümü, her görüntü işlendikten sonra sayacı azaltır. Ana uygulama belirtilen dizinden geçtikten sonra, bu `countdown_event` nesnenin sayacının sıfıra ulaşmış olduğunu işaret etmek için bekler.

Aşağıdaki örnek, `countdown_event` sınıfını göstermektedir:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[Üst](#top)]

##  <a name="complete"></a>Tüm örnek

Aşağıdaki kod, tüm örneği göstermektedir. İşlevi, GDI+ kitaplığını yönetir ve `Sample Pictures` dizindeki JPEG dosyalarını `ProcessImages` işlemek için işlevini çağırır. `wmain`

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

Aşağıdaki çizimde örnek çıkış gösterilmektedir. Her kaynak görüntü, kendisine karşılık gelen değiştirilmiş görüntünün üzerinde.

Örnek ![Için örnek çıktı] Örnek (../../parallel/concrt/media/concrt_imageout.png "Için örnek çıktı")

`Lighthouse`, Tom Alphin tarafından yazılır ve bu nedenle gri tonlamaya dönüştürülür. `Chrysanthemum`,,, ve`Tulips` baskın renk olarak kırmızı ve bu nedenle mavi ve yeşil renk bileşenleri kaldırılmış ve `Desert`koyulaştırılan `Koala`. `Hydrangeas`, `Jellyfish`, ve `Penguins` Varsayılan ölçütlere göre eşleşir ve bu nedenle, yarı PIA alınır.

[[Üst](#top)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış `image-processing-network.cpp` bir dosyaya yapıştırın ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**CL. exe/DUNıCODE/EHsc image-Processing-Network. cpp/link Gdiplus. lib**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

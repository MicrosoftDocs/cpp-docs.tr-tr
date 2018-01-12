---
title: "İzlenecek yol: bir görüntü işleme ağı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b709179cb5bc0fefa3f342374c792656fa1e934
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-an-image-processing-network"></a>İzlenecek yol: Görüntü İşleme Ağı Oluşturma
Bu belgenin, görüntü işlemeyi gerçekleştirmek zaman uyumsuz ileti blokları bir ağ oluşturmak gösterilmiştir.  
  
 Ağ onun özelliklerini temel alarak görüntüdeki gerçekleştirmek için hangi işlemleri belirler. Bu örnekte *veri akışı* rota görüntülerine ağ üzerinden model. Veri akışı modelinde iletileri göndererek bağımsız bir program bileşenlerinin birbirleriyle iletişim. Bir bileşen bir ileti aldığında, bu bazı eylemler gerçekleştirme ve başka bir bileşen daha sonra bu eylemin sonucu geçirin. Bu karşılaştırma *kontrol akışı* modeli, hangi uygulama kullanan denetim yapıları, örneğin, koşullu deyimler, döngüler ve benzeri işlemlerin bir programda sırasını denetlemek için.  
  
 Üzerinde veri akışı tabanlı bir ağ oluşturur bir *ardışık düzen* görevler. Her aşama ardışık genel görevinin parçası eşzamanlı olarak gerçekleştirir. Benzetme bu otomobil üretim için bir derleme satırdır. Her araç derleme satırın geçerken bir istasyon çerçeve derler, başka bir altyapısı vb. yükler. Aynı anda birleştirilen birden çok taşıtlardan etkinleştirerek, derleme satır aynı anda tam taşıtlardan bir birleştirme daha iyi verimlilik sağlar.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:  
  
-   [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
-   [İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)  
  
 Ayrıca, temel bilgileri anladığınızdan öneririz [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] bu kılavuza başlamadan önce.  
  
##  <a name="top"></a>Bölümler  
 Bu kılavuz aşağıdaki bölümleri içerir:  
  
-   [Görüntü işleme işlevleri tanımlama](#functionality)  
  
-   [Görüntü işleme ağı oluşturma](#network)  
  
-   [Tam bir örnek](#complete)  
  
##  <a name="functionality"></a>Görüntü işleme işlevleri tanımlama  
 Bu bölümde diskten okunan görüntüleri ile çalışmak için görüntü işleme ağı kullanır destek işlevlerini gösterir.  
  
 Aşağıdaki işlevleri `GetRGB` ve `MakeColor`, ayıklar ve belirli bir renk tek tek bileşenlerini sırasıyla birleştirir.  
  
 [!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]  
  

 Aşağıdaki işlevi `ProcessImage`, çağrıları verilen [std::function](../../standard-library/function-class.md) her piksel renk değerini dönüştürmek için nesne bir [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [bit eşlem](https://msdn.microsoft.com/library/ms534420.aspx) nesnesi. `ProcessImage` İşlev kullandığı [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) paralel eşleminde her satır işlemek için algoritması.  

  
 [!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]  
  
 Aşağıdaki işlevleri `Grayscale`, `Sepiatone`, `ColorMask`, ve `Darken`, çağrı `ProcessImage` her piksel renk değerini dönüştürmek için işlev bir `Bitmap` nesnesi. Bu işlevlerin her biri bir lambda ifadesi bir piksel renk dönüşümü tanımlamak için kullanır.  
  
 [!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]  
  
 Aşağıdaki işlevi `GetColorDominance`, ayrıca çağırır `ProcessImage` işlevi. Bununla birlikte, her renk değerinin değiştirilmesi yerine bu işlev kullanır [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) kırmızı, yeşil veya mavi renk bileşeni görüntü dominates olup olmadığını işlem nesnelere.  
  
 [!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]  
  
 Aşağıdaki işlevi `GetEncoderClsid`, sınıf tanımlayıcısı bir kodlayıcı belirtilen MIME türünü alır. Uygulama bu işlev bir bit eşlem kodlayıcıdan almak için kullanır.  
  
 [!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="network"></a>Görüntü işleme ağı oluşturma  
 Bu bölümde bir ağ üzerinde görüntü işleme gerçekleştirmek zaman uyumsuz ileti blokları oluşturma açıklar her [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] belirli bir dizinde (.jpg) görüntüsü. Ağ aşağıdaki görüntü işleme işlemleri gerçekleştirir:  
  
1.  Zel tarafından yazılan herhangi bir görüntü için gri tonlamalı dönüştürün.  
  
2.  Baskın rengi kırmızı sahip herhangi bir görüntü için yeşil ve mavi bileşenleri kaldırın ve ardından koyu.  
  
3.  Sepya tonlama diğer herhangi bir görüntü için geçerlidir.  
  
 Ağ, aşağıdaki durumlardan birinde eşleşen yalnızca ilk görüntü işleme işlemi uygular. Örneğin, bir görüntü zel tarafından yazılan ve kırmızı baskın rengini olarak varsa, görüntüyü yalnızca gri tonlamalı dönüştürülür.  
  
 Ağ her görüntü işleme işlemi gerçekleştirdikten sonra bir bit eşlem (.bmp) dosyası olarak diske resmi kaydeder.  
  
 Aşağıdaki adımlar bu görüntü işleme ağı uygulayan ve o ağ geçerli bir işlev oluşturma gösterir her [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] belirli bir dizinde görüntü.  
  
#### <a name="to-create-the-image-processing-network"></a>Görüntü işleme ağı oluşturma  
  
1.  Bir işlev oluşturun `ProcessImages`, diskte, bir dizinin adını alır.  
  
     [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]  
  
2.  İçinde `ProcessImages` işlev, oluşturma bir `countdown_event` değişkeni. `countdown_event` Sınıfı, bu kılavuzda daha sonra gösterilir.  
  
     [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]  
  
3.  Oluşturma bir [std::map](../../standard-library/map-class.md) ilişkilendirir nesnesi bir `Bitmap` özgün dosya adına sahip nesne.  
  
     [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]  
  
4.  Görüntü işleme ağı üyelerini tanımlamak için aşağıdaki kodu ekleyin.  
  
     [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]  
  
5.  Ağa bağlanmak için aşağıdaki kodu ekleyin.  
  
     [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]  
  
6.  Ağ head için her birinin tam yolunu göndermek için aşağıdaki kodu ekleyin [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] dizinde dosya.  
  
     [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]  
  
7.  Bekle `countdown_event` sıfır ulaşması değişkeni.  
  
     [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]  
  
 Aşağıdaki tabloda ağ üyeleri açıklanmaktadır.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`load_bitmap`|A [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) yükler nesnesi bir `Bitmap` nesne diskten ve bir giriş eklemeden `map` görüntü özgün dosya adıyla ilişkilendirmek için nesne.|  
|`loaded_bitmaps`|A [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) yüklenen görüntü için görüntü işleme filtreleri gönderir nesnesi.|  
|`grayscale`|A `transformer` gri tonlamalı zel tarafından yazılan görüntüleri dönüştürür Nesne. Görüntü meta verilerini, yazarı belirlemek için kullanır.|  
|`colormask`|A `transformer` baskın rengi kırmızı sahip görüntüleri yeşil ve mavi renk bileşenlerini kaldırır nesnesi.|  
|`darken`|A `transformer` baskın rengi kırmızı sahip görüntüleri koyulaştırır nesnesi.|  
|`sepiatone`|A `transformer` sepya tonlama zel tarafından yazılmaz ve daha kırmızı olmayan görüntüler için uygulanan nesnesi.|  
|`save_bitmap`|A `transformer` işlenen kaydeder nesne `image` bir bit eşlem olarak diske. `save_bitmap`Özgün dosya adını alır `map` nesne ve .bmp için dosya adı uzantısını değiştirir.|  
|`delete_bitmap`|A `transformer` görüntüleri için bellek boşaltır nesnesi.|  
|`decrement`|A [concurrency::call](../../parallel/concrt/reference/call-class.md) ağ terminal düğüm olarak davranan nesnesi. Bunu azaltır `countdown_event` görüntüyü işlenmiş olan ana uygulama sinyal nesnesi.|  
  
 `loaded_bitmaps` İleti arabelleği önemlidir çünkü, olarak bir `unbounded_buffer` nesnesi, sunduğu `Bitmap` birden çok alıcı nesnelere. Hedef blok ne zaman kabul bir `Bitmap` nesnesi `unbounded_buffer` nesnesi değil sunar, `Bitmap` diğer hedefler için nesne. Bu nedenle, hangi bağlantı sipariş nesneleri için bir `unbounded_buffer` nesne önemlidir. `grayscale`, `colormask`, Ve `sepiatone` ileti blokları her kabul etmek için bir filtre kullanmak yalnızca belirli `Bitmap` nesneleri. `decrement` İleti arabelleği önemli bir hedefi olan `loaded_bitmaps` tüm kabul ettiğinden arabellek ileti `Bitmap` bir ileti arabelleklerinin tarafından reddedilen nesneleri. Bir `unbounded_buffer` nesne sırasındaki iletilere yayılması için gereklidir. Bu nedenle, bir `unbounded_buffer` nesne yeni bir hedef blok ona bağlı ve geçerli bir hedef blok bu iletiyi kabul ederse iletisini kabul eden kadar engeller.  
  
 Uygulamanız birden çok ileti blokları işlemi yalnızca ilk iletisini kabul eden bir ileti bloğu yerine ileti gerektiriyorsa başka bir ileti blok türü gibi kullanabilir `overwrite_buffer`. `overwrite_buffer` Sınıf, bir kerede tek bir ileti içerir, ancak bu ileti her hedeflerine yayar.  
  
 Görüntü işleme ağı aşağıda gösterilmiştir:  
  
 ![Görüntü işleme ağı](../../parallel/concrt/media/concrt_imageproc.png "concrt_imageproc")  
  
 `countdown_event` Nesne bu örnekte tüm görüntüleri işlendiğinde ana uygulama bildirmek görüntü işleme ağı sağlar. `countdown_event` Sınıfını kullanan bir [concurrency::event](../../parallel/concrt/reference/event-class.md) bir sayaç değeri sıfır ulaştığında sinyal nesnesi. Olan bir dosya adı ağ gönderir her zaman ana uygulama sayaç artırılır. Ağ azaltır terminal düğümünün her görüntü işlendikten sonra sayacı. Belirtilen dizin ana uygulama eriştikten sonra onu bekler `countdown_event` kendi sayaç sıfır ulaştı sinyal nesnesi.  
  
 Aşağıdaki örnekte gösterildiği `countdown_event` sınıfı:  
  
 [!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="complete"></a>Tam bir örnek  
 Aşağıdaki kod, tam bir örnek gösterilir. `wmain` İşlevi yönetir [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] kitaplığı ve çağrıları `ProcessImages` işlev işleme [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] dosyalar `Sample Pictures` dizin.  
  
 [!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]  
  
 Örnek çıktı aşağıda gösterilmektedir. Her kaynak görüntü, karşılık gelen değiştirilmiş görüntüsüdür.  
  
 ![Örnek çıktı örneğin](../../parallel/concrt/media/concrt_imageout.png "concrt_imageout")  
  
 `Lighthouse`zel Alphin tarafından yazılan ve bu nedenle gri tonlamalı dönüştürülür. `Chrysanthemum`, `Desert`, `Koala`, ve `Tulips` baskın rengi kırmızı varsa ve bu nedenle sahip kaldırılan mavi ve yeşil renk bileşenlerini ve koyu. `Hydrangeas`, `Jellyfish`, ve `Penguins` varsayılan ölçütlere uyan ve bu nedenle toned sepya.  
  
 [[Üst](#top)]  
  
### <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `image-processing-network.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /DUNICODE /EHsc görüntü işleme network.cpp/Link gdiplus.lib**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

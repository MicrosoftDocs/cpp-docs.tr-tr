---
title: 'Başvuru: Windows Performans Çözümleyicisi görünümleri'
description: C++ Build Insights görünümleri için Başvuru, Windows Performans Çözümleyicisi'nde kullanılabilir.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b54b1b76d83b77ec7b8d8d3309d81ed9eb2db2d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323229"
---
# <a name="reference-windows-performance-analyzer-views"></a>Başvuru: Windows Performans Çözümleyicisi görünümleri

::: moniker range="<=vs-2017"

C++ Build Insights araçları Visual Studio 2019'da mevcuttur. Bu sürümün belgelerini görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

Bu makalede, Windows Performans Çözümleyicisi'nde (WPA) bulunan C++ Build Insights görünümlerinin her biri hakkında ayrıntılı bilgi verilmektedir. Bulmak için bu sayfayı kullanın:

- veri sütunu açıklamaları; Ve
- kullanım ları ve tercih edilen görüntüleme modu da dahil olmak üzere her görünüm için kullanılabilir hazır ayarlar.

WPA'da yeniyseniz, öncelikle [C++ Build Insights için WPA'nın temellerini](/cpp/build-insights/tutorials/wpa-basics)anlamanızı öneririz.

## <a name="build-explorer"></a>Explorer oluştur

Yapı Gezgini görünümü aşağıdakiler için kullanılır:

- paralellik konularını teşhis etmek,
- yapı sürenizin ayrıştırma, kod oluşturma veya bağlama tarafından baskın olup olmadığını belirlemek ve
- darboğazları ve alışılmadık uzun yapı etkinliklerini tanımlar.

### <a name="build-explorer-view-data-columns"></a>Explorer görünüm veri sütunları oluşturma

| Sütun Adı | Açıklama |
|-|-|
| BuildTimelineDescription | Geçerli etkinliğin veya özelliğin oluştuğu zaman çizelgesini metinsel bir açıklama. |
| BuildTimelineId          | Geçerli etkinliğin veya özelliğin bulunduğu zaman çizelgesi için sıfır tabanlı bir tanımlayıcı. |
| Bileşen                | Geçerli olay yayımlandığında derlenen veya bağlanan bileşen. Bu sütunun değeri, hiçbir bileşen bu olayla ilişkilendirilmediğinde * \<Çağrı X\> Bilgisi'dir.* X, olayın yayımlandığı anda gerçekleştirilen çağırma için benzersiz bir sayısal tanımlayıcıdır. Bu tanımlayıcı, bu olay için InvocationId sütunundakiyle aynıdır. |
| Sayı                    | Bu veri satırı tarafından temsil edilen etkinlik veya özellik sayısı. Bu değer her zaman 1'dir ve yalnızca birden çok satır gruplandığında toplama senaryolarında yararlıdır. |
| ExclusiveCPUTime         | Bu etkinlik tarafından kullanılan milisaniye cinsinden CPU süresi miktarı. Çocuk etkinliklerinde harcanan süre bu tutara dahil değildir. |
| ÖzelSüre        | Etkinliğin milisaniye süresi. Çocuk etkinliklerinin süresi bu tutara dahil değildir. |
| Kapsayıcı CPUTime         | Bu etkinlik ve tüm alt etkinlikler tarafından kullanılan milisaniye cinsinden CPU süresi miktarı. |
| Dahil Süresi        | Tüm çocuk etkinlikleri de dahil olmak üzere bu etkinliğin milisaniye süresi. |
| InvocationDescription    | Bu olayın gerçekleştiği çağırmanın metinsel bir açıklaması. Açıklama *cl.exe* veya *link.exe*olup olmadığını ve benzersiz bir sayısal çağırma tanımlayıcısı içerir. Varsa, çağırma sırasında derlenen veya bağlanan bileşene giden tam yolu içerir. Herhangi bir bileşen oluşturmayan çağırmalar veya birden çok bileşen oluşturanlar için yol boştur. Çağırma tanımlayıcısı, InvocationId sütunundakiyle aynıdır. |
| İptal             | Bu olay meydana gelen çağırma için benzersiz bir sayısal tanımlayıcı. |
| Adı                     | Bu olaytarafından temsil edilen etkinliğin veya özelliğin adı. |
| Zaman                     | Olayın ne zaman oluştuğunu tanımlayan bir zaman damgası. |
| Araç                     | Bu olay oluştuğunda çalıştırılan araç. Bu sütunun değeri CL veya Link'tir. |
| Tür                     | Geçerli olayın türü. Bu değer Etkinlik veya Özellik'tir. |
| Değer                    | Geçerli olay bir özellikse, bu sütun değerini içerir. Geçerli olay bir etkinlik olduğunda bu sütun boş bırakılır. |

### <a name="build-explorer-view-presets"></a>Explorer görünümü ön ayarlarını oluşturun

| Önceden Ayarlanmış Ad           | Tercih Edilen Görünüm Modu | Nasıl Kullanılır? |
|-----------------------|---------------------|------------|
| Faaliyet İstatistikleri   | Grafik / Tablo       | Tüm Yapı Gezgini etkinlikleri için toplanan istatistikleri görüntülemek için bu önceden ayarlanmışı kullanın. Tablo modunda, yapınızın ayrıştırma, kod oluşturma veya bağlayıcı tarafından yönetilip yönetilemeyeceğini bir bakışta söyleyin. Her etkinlik için toplanan süreler azalan sırada sıralanır. Bu üst etkinlikler için en fazla zamanı hangi çağrıların alacağını kolayca bulmak için üst düğümü genişleterek delinin. İsterseniz, wpa ayarlarını ortalamaları veya diğer toplama türlerini gösterecek şekilde ayarlayabilirsiniz. Grafik modunda, yapınız sırasında her etkinliğin etkin olup olmadığını görün. |
| Davetler           | Graf               | Başlangıç saatine göre sıralanmış grafik görünümündeki çağrıların bir listesini aşağı kaydırın. Düşük CPU kullanım bölgeleriyle uyumlu çağrıları bulmak için CPU (Örneklenmiş) görünümüyle birlikte kullanabilirsiniz. Paralellik sorunlarını algıla. |
| Çağırma Özellikleri | Tablo               | Belirli bir derleyici veya bağlayıcı çağırma yla ilgili önemli bilgileri hızla bulun. Sürümünü, çalışma dizini veya çağırmak için kullanılan tam komut satırını belirleyin. |
| Zaman çizelgeleri             | Graf               | Yapınızın nasıl paralelleştirildigine ait bir çubuk grafiğine bakın. Paralellik sorunlarını ve darboğazları bir bakışta belirleyin. WPA'yı gereksinimlerinize göre çubuklara farklı anlamlar atayacak şekilde yapılandırın. Tüm çağrılarınızın renk kodlu çubuk grafiğini görüntülemek için son gruplanmış sütun olarak çağrı açıklamaları seçin. Zaman alıcı suçluları hızlı bir şekilde belirlemenize yardımcı olur. Ardından, yakınlaştırın ve en uzun parçaları görmek için son gruplanmış sütun olarak etkinlik adını seçin. |

## <a name="files"></a>Dosyalar

Dosyalar görünümü için kullanılır:

- üstenlerin en sık dahil edildiğini belirlemek ve
- önceden derlenmiş bir üstbilgiye (PCH) ne ekleyeceğine karar vermenize yardımcı olur.

### <a name="files-view-data-columns"></a>Dosyaları görüntüle veri sütunları

| Sütun Adı              | Açıklama |
|--------------------------|-------------|
| Etkinlik Adı             | Bu dosya olayı yayımlandığında devam eden etkinlik. Şu anda, bu değer her zaman *Ayrıştırma.* |
| BuildTimelineDescription | * |
| BuildTimelineId          | * |
| Bileşen                | * |
| Sayı                    | * |
| Derinlik                    | Bu dosyanın bulunduğu dahil ağacındaki sıfır tabanlı konum. Sayma, include ağacının kökünden başlar. 0 değeri genellikle bir .c/.cpp dosyasına karşılık gelir. |
| ÖzelSüre        | * |
| Buna dahil               | Geçerli dosyayı içeren dosyanın tam yolu. |
| DahilYol             | Geçerli dosyanın tam yolu. |
| Dahil Süresi        | * |
| İptal             | * |
| StartTime                | Geçerli dosya olayının yayımlandığı zamanı gösteren bir zaman damgası. |
| Araç                     | * |

\*Bu sütunun değeri [Yapı Gezgini](#build-explorer-view-data-columns) görünümündekiyle aynıdır.

### <a name="files-view-presets"></a>Dosyaları görünüm ön ayarları

| Önceden Ayarlanmış Ad | Tercih Edilen Görünüm Modu | Nasıl Kullanılır? |
|-------------|---------------------|------------|
| İstatistikler  | Tablo               | Listeye azalan sırada bakarak hangi dosyaların en yüksek toplu ayrıştırma süresine sahip olduğunu görün. Üstbilgilerinizi yeniden yapılandırmanıza veya PCH'nize ne ekleyeceğine karar vermenize yardımcı olmak için bu bilgileri kullanın. |

## <a name="functions"></a>İşlevler

İşlevler görünümü, aşırı uzun kod oluşturma süresine sahip işlevleri tanımlamak için kullanılır.

### <a name="functions-view-data-columns"></a>Fonksiyonlar veri sütunlarını görüntüleme

| Sütun Adı              | Açıklama |
|--------------------------|-------------|
| Etkinlik Adı             | Bu işlev olayı yayımlandığında devam eden etkinlik. Şu anda, bu değer her zaman *CodeGeneration*olduğunu. |
| BuildTimelineDescription | * |
| BuildTimelineId          | * |
| Bileşen                | * |
| Sayı                    | * |
| Süre                 | Bu işlev için kod oluşturma etkinliğinin süresi. |
| Fonksiyon Adı             | Kod oluşturma sürecinden geçen işlevin adı. |
| İptal             | * |
| StartTime                | Geçerli işlev olayının ne zaman yayıldığını gösteren bir zaman damgası. |
| Araç                     | * |

\*Bu sütunun değeri [Yapı Gezgini](#build-explorer-view-data-columns) görünümündekiyle aynıdır.

### <a name="functions-view-presets"></a>İşlevler ön ayarları görüntüleme

| Önceden Ayarlanmış Ad | Tercih Edilen Görünüm Modu | Nasıl Kullanılır? |
|-------------|---------------------|------------|
| İstatistikler  | Tablo               | Listeye azalan sırada bakarak hangi işlevlerin en yüksek toplu kod oluşturma süresine sahip olduğunu görün. Bunlar, kodunuzun **__forceinline** anahtar sözcüğü nerede kullandığını veya bazı işlevlerin çok büyük olabileceğini belirtebilirler. |
| Zaman çizelgeleri   | Graf               | Oluşturmak için en çok zaman alan işlevlerin konumunu ve süresini öğrenmek için bu çubuk grafiğine bakın. Yapı Gezgini görünümündeki darboğazlarla uyumlu olup olmadıklarını görün. Bunu yaparlarsa, kod oluşturma sürelerini azaltmak ve yapı sürelerinizden yararlanmak için uygun eylemi gerçekleştirin. |

## <a name="see-also"></a>Ayrıca bkz.

[C++ Build Insights ile başlayın](/cpp/build-insights/get-started-with-cpp-build-insights)\
[Referans: vcperf komutları](vcperf-commands.md)\
[Öğretici: Windows Performans Çözümleyicisi temelleri](/cpp/build-insights/tutorials/wpa-basics)\
[Windows Performans Analizörü](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end

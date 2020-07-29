---
title: 'Başvuru: Windows Performans Çözümleyici görünümleri'
description: Windows Performans Çözümleyici 'de kullanılabilen C++ derleme öngörüleri görünümleri için başvuru.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8bbcc43ef19adfd85a3679a2136d471333a74a10
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224103"
---
# <a name="reference-windows-performance-analyzer-views"></a>Başvuru: Windows Performans Çözümleyici görünümleri

::: moniker range="<=vs-2017"

C++ derleme öngörüleri araçları Visual Studio 2019 'de bulunabilir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

Bu makalede, Windows Performans Çözümleyicisi 'nde (WPA) kullanılabilen C++ derleme öngörüleri görünümlerinin her biri hakkında ayrıntılı bilgi verilmektedir. Bulmak için bu sayfayı kullanın:

- veri sütunu açıklamaları; '
- tasarlanan kullanımları ve tercih edilen görüntüleme modunu içeren her bir görünüm için kullanılabilir Önayarlar.

WPA 'yı yeni kullanmaya başladıysanız, öncelikle [C++ derleme öngörülerine YÖNELIK WPA temellerini](/cpp/build-insights/tutorials/wpa-basics)öğrenmeniz önerilir.

## <a name="build-explorer"></a>Yapı Gezgini

Yapı Gezgini görünümü şu şekilde kullanılır:

- paralellik sorunları tanılayın,
- derleme süresinin ayrıştırılmasından, kod oluşturmaya veya bağlamaya göre olup olmadığını belirleme ve
- darboğazları ve alışılmadık uzun oluşturma etkinliklerini belirleyin.

### <a name="build-explorer-view-data-columns"></a>Yapı Gezgini görünüm verileri sütunları

| Sütun adı | Açıklama |
|-|-|
| BuildTimelineDescription | Bir metinsel açıklaması geçerli etkinliğin veya özelliğin gerçekleştiği zaman çizelgesi. |
| Buildtimelineıd          | Geçerli etkinliğin veya özelliğin gerçekleştiği zaman çizelgesi için sıfır tabanlı tanımlayıcı. |
| Bileşen                | Geçerli olay yayıldıysa derlenen veya bağlanan bileşen. Bu sütunun değeri, *\<Invocation X Info\>* Bu olayla hiçbir bileşen ilişkilendirilmediği zaman olur. X, olay yayınlanma sırasında yürütülen çağrının benzersiz bir sayısal tanımlayıcısıdır. Bu tanımlayıcı, bu olay için ınvocationıd sütunundaki bir ile aynıdır. |
| Count                    | Bu veri satırıyla temsil edilen etkinlik veya özellik sayısı. Bu değer her zaman 1 ' dir ve yalnızca birden fazla satır gruplandırılırken toplama senaryolarında faydalıdır. |
| ExclusiveCPUTime         | Bu etkinlik tarafından kullanılan milisaniye cinsinden CPU zamanı miktarı. Alt etkinliklerde harcanan süre bu tutara dahil değildir. |
| ExclusiveDuration        | Etkinliğin milisaniyelik süresi. Alt etkinliklerin süresi bu tutara dahil değildir. |
| Yani ıvecputime         | Bu etkinlik ve tüm alt etkinlikler tarafından kullanılan milisaniye cinsinden CPU zamanı miktarı. |
| Yani, Iveduration        | Bu etkinliğin tüm alt etkinlikler dahil olmak üzere milisaniyelik süresi. |
| Incationdescription    | Bu olayın oluştuğu çağrının metinsel açıklaması. Açıklama *cl.exe* veya *link.exe*ve benzersiz bir sayısal çağrı tanımlayıcısı olup olmadığını içerir. Uygulanabiliyorsa, bu, çağırma sırasında derlenen veya bağlanan bileşenin tam yolunu içerir. Herhangi bir bileşen veya birden çok bileşen oluşturan çağrılar için, yol boş olur. Çağırma tanımlayıcısı, ınvocationıd sütunundaki ile aynıdır. |
| Invocationıd             | Bu olayın oluştuğu çağrı için benzersiz bir sayısal tanımlayıcı. |
| Ad                     | Bu olayla temsil edilen etkinliğin veya özelliğin adı. |
| Zaman                     | Olayın ne zaman oluştuğunu belirleyen zaman damgası. |
| Araç                     | Bu olay oluştuğunda yürütülen araç. Bu sütunun değeri CL ya da LINK. |
| Tür                     | Geçerli olayın türü. Bu değer, etkinlik ya da özellik. |
| Değer                    | Geçerli olay bir özellik ise, bu sütun değerini içerir. Bu sütun, geçerli olay bir etkinlik olduğunda boş bırakılır. |

### <a name="build-explorer-view-presets"></a>Yapı Gezgini görünümü ön ayarları

| Önceden ayarlanmış ad           | Tercih edilen görünüm modu | Nasıl kullanılır |
|-----------------------|---------------------|------------|
| Etkinlik Istatistikleri   | Grafik/tablo       | Tüm derleme Gezgini etkinliklerinin toplu istatistiklerini görüntülemek için bu ön ayarı kullanın. Tablo modunda, derlemeniz, kod üretimi veya bağlayıcı tarafından ayrıştırıldığında, bir bakışta anlatın. Her etkinlik için toplanan süreler azalan düzende sıralanır. Bu en fazla etkinlik için en çok hangi etkinleştirmeleri olduğunu kolayca bulmak üzere en üstteki düğümü genişleterek detaydan yararlanın. İsterseniz, WPA ayarlarını, ortalamaları veya diğer toplama türlerini gösterecek şekilde ayarlayabilirsiniz. Grafik modunda, derleme sırasında her bir etkinliğin etkin olduğu zaman bölümüne bakın. |
| Çağrıları           | Graf               | Grafik görünümünde başlangıç zamanına göre sıralanan bir çağırma listesi boyunca aşağı doğru kaydırın. Düşük CPU kullanım bölgeleriyle hizalamakta olan çağırmaları bulmak için CPU (örneklenmiş) görünümüyle birlikte kullanabilirsiniz. Paralellik sorunları tespit edin. |
| Çağırma özellikleri | Tablo               | Belirli bir derleyici veya bağlayıcı çağırma hakkında önemli bilgileri hızlıca bulun. Sürümünü, çalışma dizinini veya çağırmak için kullanılan tam komut satırını saptayın. |
| Zaman çizelgeleri             | Graf               | Yapılarınızın nasıl paralelleştirilmesine ilişkin bir çubuk grafiğine bakın. Paralellik sorunları ve darboğazları bir bakışta belirleyin. WPA 'Yı gereksinimlerinize göre çubuklara farklı anlamlara atamak için yapılandırın. Tüm çağrılarınızın renk kodlu çubuk grafiğini görüntülemek için, son gruplanmış sütun olarak çağırma açıklamaları ' nı seçin. Zaman alan kültları hızla tanımanıza yardımcı olur. Ardından, en uzun parçaları görmek için, yakınlaştırın ve son gruplanmış sütun olarak etkinlik adını seçin. |

## <a name="files"></a>Dosyalar

Dosyalar görünümü şu şekilde kullanılır:

- en sık hangi üstbilgilerin ekleneceğini belirleme ve
- önceden derlenmiş bir üstbilgiye (PCH) nelerin dahil edileceğini belirlemenize yardımcı olun.

### <a name="files-view-data-columns"></a>Dosya görünümü veri sütunları

| Sütun adı              | Açıklama |
|--------------------------|-------------|
| Özelliğinde             | Bu dosya olayı yayıldıysa devam eden etkinlik. Şu anda bu değer her zaman *Ayrıştırılmamaktadır*. |
| BuildTimelineDescription | * |
| Buildtimelineıd          | * |
| Bileşen                | * |
| Count                    | * |
| Derinliğini                    | Bu dosyanın bulunduğu ekleme ağacındaki sıfır tabanlı konum. Sayma, ekleme ağacının kökünde başlar. 0 değeri tipik olarak bir. c/. cpp dosyasına karşılık gelir. |
| ExclusiveDuration        | * |
| Includedby               | Geçerli dosyayı içeren dosyanın tam yolu. |
| Includedpath             | Geçerli dosyanın tam yolu. |
| Yani, Iveduration        | * |
| Invocationıd             | * |
| StartTime                | Geçerli dosya olayının yayıldığını temsil eden zaman damgası. |
| Araç                     | * |

\*Bu sütunun değeri, [Yapı Gezgini](#build-explorer-view-data-columns) görünümündeki ile aynıdır.

### <a name="files-view-presets"></a>Dosya görünümü önayarları

| Önceden ayarlanmış ad | Tercih edilen görünüm modu | Nasıl kullanılır |
|-------------|---------------------|------------|
| İstatistikler  | Tablo               | Listeye azalan sırada bakarak en yüksek ayrıştırma zamanına sahip dosyaları görün. Bu bilgileri, başlıklarınızı yeniden yapılandırmak veya PCH 'nize nelerin dahil edileceğini belirlemek için kullanın. |

## <a name="functions"></a>İşlevler

Işlevler görünümü aşırı uzun kod oluşturma süresine sahip işlevleri belirlemek için kullanılır.

### <a name="functions-view-data-columns"></a>İşlevler veri sütunlarını görüntüle

| Sütun adı              | Açıklama |
|--------------------------|-------------|
| Özelliğinde             | Bu işlev olayı yayıldıysa sürmekte olan etkinlik. Şu anda bu değer her zaman *CodeGeneration*değeridir. |
| BuildTimelineDescription | * |
| Buildtimelineıd          | * |
| Bileşen                | * |
| Count                    | * |
| Süre                 | Bu işlev için kod oluşturma etkinliğinin süresi. |
| Ifadelerini             | Kod üretimi yapılmakta olan işlevin adı. |
| Invocationıd             | * |
| StartTime                | Geçerli işlev olayının ne zaman yayıldığını temsil eden zaman damgası. |
| Araç                     | * |

\*Bu sütunun değeri, [Yapı Gezgini](#build-explorer-view-data-columns) görünümündeki ile aynıdır.

### <a name="functions-view-presets"></a>İşlevler görünümü önayarları

| Önceden ayarlanmış ad | Tercih edilen görünüm modu | Nasıl kullanılır |
|-------------|---------------------|------------|
| İstatistikler  | Tablo               | Listeye azalan sırada bakarak, hangi işlevlerin en yüksek toplu kod oluşturma süresine sahip olduğunu görün. **`__forceinline`** Bu kişiler, kodunuzun anahtar sözcüğünü aşırı kullandığı veya bazı işlevlerin çok büyük olabileceği ipucu edebilir. |
| Zaman çizelgeleri   | Graf               | En uzun sürede oluşturma işlevlerinin konumunu ve süresini öğrenmek için bu çubuk grafiğine bakın. Yapı Gezgini görünümünde performans sorunlarını nasıl hizaladıklarından öğrenin. Mümkünse, kod oluşturma süresini azaltmak ve derleme zamanlarınızın avantajını yapmak için uygun işlemleri gerçekleştirin. |

## <a name="see-also"></a>Ayrıca bkz.

[C++ Build Insights 'ı kullanmaya başlama](/cpp/build-insights/get-started-with-cpp-build-insights)\
[Reference: vcperf komutları](vcperf-commands.md)\
[Öğretici: Windows Performans Çözümleyicisi temelleri](/cpp/build-insights/tutorials/wpa-basics)\
[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end

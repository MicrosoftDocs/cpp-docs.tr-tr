---
title: 'Reference: vcperf komutları'
description: Komut satırı yardımcı programı için başvuru vcperf.exe.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 42ca422e11824bdbdad4e42e7b55950317095703
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922211"
---
# <a name="reference-vcperf-commands"></a>Reference: vcperf komutları

::: moniker range="<=msvc-150"

C++ derleme öngörüleri araçları Visual Studio 2019 'de bulunabilir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="msvc-160"

Bu makale *vcperf.exe* ' de kullanılabilen komutları ve bunların nasıl kullanılacağını listeler ve açıklar.

## <a name="commands-to-start-and-stop-traces"></a>İzlemeleri başlatma ve durdurma komutları

*ÖNEMLI: aşağıdaki komutların tümü yönetici ayrıcalıkları gerektirir.*

| Seçenek           | Bağımsız değişkenler ve açıklama |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | *vcperf.exe* , verilen oturum adı altında bir izleme başlatmasını söyler. Belirli bir makinede tek seferde yalnızca bir etkin oturum olabilir. <br/><br/> `/nocpusampling`Seçenek belirtilmişse *vcperf.exe* CPU örnekleri toplanmaz. Windows Performans Çözümleyicisi 'nde CPU kullanımı (örneklenmiş) görünümünün kullanımını engeller, ancak toplanan izlemeler daha küçük hale gelir. <br/><br/> İzleme başlatıldıktan sonra *vcperf.exe* hemen döndürülür. Olaylar, makinede çalışan tüm işlemlerin sistem genelinde toplanmaktadır. Diğer bir deyişle, *vcperf.exe* çalıştırmak için kullandığınız bir komut isteminden projenizi oluşturmanız gerekmez. Örneğin, projenizi Visual Studio 'dan oluşturabilirsiniz. |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | Verilen oturum adı tarafından tanımlanan izlemeyi sonlandırır. Windows Performans Çözümleyicisi 'nde (WPA) görüntülenebilen bir dosya oluşturmak için izlemede işleme sonrası bir adım çalıştırır. En iyi görüntüleme deneyimi için, C++ derleme öngörüleri eklentisini içeren bir WPA sürümü kullanın. Daha fazla bilgi için bkz. [C++ Build Insights ile çalışmaya başlama](../get-started-with-cpp-build-insights.md). `<outputFile.etl>`Parametresi, çıktı dosyasının kaydedileceği yeri belirtir. |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | Verilen oturum adı tarafından tanımlanan izlemeyi sonlandırır ve belirtilen çıkış dosyasına ham, işlenmemiş verileri yazar. Elde edilen dosya WPA 'da görüntülenmek üzere tasarlanmamıştır. <br/><br/> Komutta yer alan işleme sonrası adım `/stop` bazen uzun olabilir. `/stopnoanalyze`Bu işleme sonrası adımını geciktirmek için komutunu kullanabilirsiniz. `/analyze`Windows Performans Çözümleyici 'de görüntülenebilir bir dosya üretmeye hazırsanız komutunu kullanın. |

## <a name="miscellaneous-commands"></a>Çeşitli komutlar

| Seçenek     | Bağımsız değişkenler ve açıklama |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | Komutu tarafından oluşturulan ham izleme dosyasını kabul eder `/stopnoanalyze` . Windows Performans Çözümleyicisi 'nde görüntülenebilen bir dosya oluşturmak için bu izlemede bir işleme sonrası adımı çalıştırır. En iyi görüntüleme deneyimi için, C++ derleme öngörüleri eklentisini içeren bir WPA sürümü kullanın. Daha fazla bilgi için bkz. [C++ Build Insights ile çalışmaya başlama](../get-started-with-cpp-build-insights.md). |

## <a name="see-also"></a>Ayrıca bkz.

[C++ Build Insights 'ı kullanmaya başlama](../get-started-with-cpp-build-insights.md)\
[Öğretici: Windows Performans Çözümleyicisi temelleri](../tutorials/wpa-basics.md)\
[Başvuru: Windows Performans Çözümleyici görünümleri](wpa-views.md)\
[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end

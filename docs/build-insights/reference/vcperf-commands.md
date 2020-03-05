---
title: 'Reference: vcperf komutları'
description: Komut satırı yardımcı programı vcperf. exe için başvuru.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b85320ce4517eb41410c59a11bd79553405b8402
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332224"
---
# <a name="reference-vcperf-commands"></a>Reference: vcperf komutları

::: moniker range="<=vs-2017"

Visual C++ Studio 2019 ' de derleme öngörüleri araçları mevcuttur. Bu sürümün belgelerini görmek için bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range="vs-2019"

Bu makalede *vcperf. exe*' de kullanılabilen komutlar ve bunların nasıl kullanılacağı açıklanmaktadır.

## <a name="commands-to-start-and-stop-traces"></a>İzlemeleri başlatma ve durdurma komutları

*ÖNEMLI: aşağıdaki komutların tümü yönetici ayrıcalıkları gerektirir.*

| Seçenek           | Bağımsız değişkenler ve açıklama |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | *Vcperf. exe* ' ye verilen oturum adı altında bir izleme başlatmasını söyler. Belirli bir makinede tek seferde yalnızca bir etkin oturum olabilir. <br/><br/> `/nocpusampling` seçeneği belirtilmişse, *vcperf. exe* CPU örnekleri toplanmaz. Windows Performans Çözümleyicisi 'nde CPU kullanımı (örneklenmiş) görünümünün kullanımını engeller, ancak toplanan izlemeler daha küçük hale gelir. <br/><br/> İzleme başlatıldıktan sonra *vcperf. exe* hemen döndürülür. Olaylar, makinede çalışan tüm işlemlerin sistem genelinde toplanmaktadır. Bu, projenizi *vcperf. exe dosyasını*çalıştırmak için kullandığınız komutla aynı komut isteminden oluşturmanıza gerek kalmaz. Örneğin, projenizi Visual Studio 'dan oluşturabilirsiniz. |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | Verilen oturum adı tarafından tanımlanan izlemeyi sonlandırır. Windows Performans Çözümleyicisi 'nde (WPA) görüntülenebilen bir dosya oluşturmak için izlemede işleme sonrası bir adım çalıştırır. En iyi görüntüleme deneyimi için, C++ derleme öngörüleri eklentisini IÇEREN bir WPA sürümü kullanın. Daha fazla bilgi için bkz. [ C++ derleme öngörülerini kullanmaya başlama](/cpp/build-insights/get-started-with-cpp-build-insights). `<outputFile.etl>` parametresi, çıktı dosyasının kaydedileceği yeri belirtir. |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | Verilen oturum adı tarafından tanımlanan izlemeyi sonlandırır ve belirtilen çıkış dosyasına ham, işlenmemiş verileri yazar. Elde edilen dosya WPA 'da görüntülenmek üzere tasarlanmamıştır. <br/><br/> `/stop` komutuna dahil olan işlem sonrası adım bazen uzun olabilir. Bu işleme sonrası adımını geciktirmek için `/stopnoanalyze` komutunu kullanabilirsiniz. Windows Performans Çözümleyici 'de görüntülenebilir bir dosya oluşturmaya hazırsanız `/analyze` komutunu kullanın. |

## <a name="miscellaneous-commands"></a>Çeşitli komutlar

| Seçenek     | Bağımsız değişkenler ve açıklama |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | `/stopnoanalyze` komutu tarafından oluşturulan ham izleme dosyasını kabul eder. Windows Performans Çözümleyicisi 'nde görüntülenebilen bir dosya oluşturmak için bu izlemede bir işleme sonrası adımı çalıştırır. En iyi görüntüleme deneyimi için, C++ derleme öngörüleri eklentisini IÇEREN bir WPA sürümü kullanın. Daha fazla bilgi için bkz. [ C++ derleme öngörülerini kullanmaya başlama](/cpp/build-insights/get-started-with-cpp-build-insights). |

## <a name="see-also"></a>Ayrıca bkz.

Build Insights 'ı kullanmaya başlayın\ [ C++ ](/cpp/build-insights/get-started-with-cpp-build-insights)
[Öğretici: Windows Performans Çözümleyicisi temelleri](/cpp/build-insights/tutorials/wpa-basics)\
[Başvuru: Windows Performans Çözümleyici görünümleri](wpa-views.md)\
[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end

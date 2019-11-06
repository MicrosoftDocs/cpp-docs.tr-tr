---
title: 'C++Derleme öngörüleri: vcperf. exe başvurusu'
description: Komut satırı yardımcı programı vcperf. exe için başvuru.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 195d115edae9947b39795440894e4f6bf0ee485e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73633100"
---
# <a name="c-build-insights-vcperfexe-reference"></a>C++Derleme öngörüleri: vcperf. exe başvurusu

::: moniker range="<=vs-2017"

Visual C++ Studio 2019 ' de derleme öngörüleri araçları mevcuttur. Bu sürümün belgelerini görmek için bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range="vs-2019"

Bu makalede *vcperf. exe*' de kullanılabilen komutlar ve bunların nasıl kullanılacağı açıklanmaktadır.

## <a name="commands-to-start-and-stop-traces"></a>İzlemeleri başlatma ve durdurma komutları

*ÖNEMLI: aşağıdaki komutların tümü yönetici ayrıcalıkları gerektirir.*

| Seçenek           | Bağımsız değişkenler ve açıklama |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]``<sessionName>` |
|                  | *Vcperf. exe* ' ye verilen oturum adı altında bir izleme başlatmasını söyler. Belirli bir makinede tek seferde yalnızca bir etkin oturum olabilir. <br/><br/> `/nocpusampling` seçeneği belirtilmişse, *vcperf. exe* CPU örnekleri toplanmaz. Windows Performans Çözümleyicisi 'nde CPU kullanımı (örneklenmiş) görünümünün kullanımını engeller, ancak toplanan izlemeler daha küçük hale gelir. <br/><br/> İzleme başlatıldıktan sonra *vcperf. exe* hemen döndürülür. Olaylar, makinede çalışan tüm işlemlerin sistem genelinde toplanmaktadır. Bu, projenizi *vcperf. exe dosyasını*çalıştırmak için kullandığınız komutla aynı komut isteminden oluşturmanıza gerek kalmaz. Örneğin, projenizi Visual Studio 'dan oluşturabilirsiniz. |
| `/stop`          | `<sessionName>``<outputFile.etl>` |
|                  | Verilen oturum adı tarafından tanımlanan izlemeyi sonlandırır. Windows Performans Çözümleyicisi 'nde (WPA) görüntülenebilen bir dosya oluşturmak için izlemede işleme sonrası bir adım çalıştırır. En iyi görüntüleme deneyimi için, C++ derleme öngörüleri eklentisini IÇEREN bir WPA sürümü kullanın. Daha fazla bilgi için bkz. [ C++ derleme öngörülerini kullanmaya başlama](get-started-with-cpp-build-insights.md). `<outputFile.etl>` parametresi, çıktı dosyasının kaydedileceği yeri belirtir. |
| `/stopnoanalyze` | `<sessionName>``<rawOutputFile.etl>` |
|                  | Verilen oturum adı tarafından tanımlanan izlemeyi sonlandırır ve belirtilen çıkış dosyasına ham, işlenmemiş verileri yazar. Elde edilen dosya WPA 'da görüntülenmek üzere tasarlanmamıştır. <br/><br/> `/stop` komutuna dahil olan işlem sonrası adım bazen uzun olabilir. Bu işleme sonrası adımını geciktirmek için `/stopnoanalyze` komutunu kullanabilirsiniz. Windows Performans Çözümleyici 'de görüntülenebilir bir dosya oluşturmaya hazırsanız `/analyze` komutunu kullanın. |

## <a name="miscellaneous-commands"></a>Çeşitli komutlar

| Seçenek     | Bağımsız değişkenler ve açıklama |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | `/stopnoanalyze` komutu tarafından oluşturulan ham izleme dosyasını kabul eder. Windows Performans Çözümleyicisi 'nde görüntülenebilen bir dosya oluşturmak için bu izlemede bir işleme sonrası adımı çalıştırır. En iyi görüntüleme deneyimi için, C++ derleme öngörüleri eklentisini IÇEREN bir WPA sürümü kullanın. Daha fazla bilgi için bkz. [ C++ derleme öngörülerini kullanmaya başlama](get-started-with-cpp-build-insights.md). |

## <a name="see-also"></a>Ayrıca bkz.

Build Insights 'ı kullanmaya başlayın\ [ C++ ](get-started-with-cpp-build-insights.md)
[Windows Performans Çözümleyici temelleri](wpa-basics.md)\
[Windows Performans Çözümleyici görünümleri başvuru](wpa-views-reference.md)\
[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end

---
title: 'Referans: vcperf komutları'
description: Komut satırı yardımcı programı vcperf.exe için başvuru.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9d3b0a9dbdfe922dc87f91006441e1f65d54c8a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323248"
---
# <a name="reference-vcperf-commands"></a>Referans: vcperf komutları

::: moniker range="<=vs-2017"

C++ Build Insights araçları Visual Studio 2019'da mevcuttur. Bu sürümün belgelerini görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

Bu *makalede, vcperf.exe'de*bulunan komutları ve bunların nasıl kullanılacağı açıklanmaktadır.

## <a name="commands-to-start-and-stop-traces"></a>İzlemeleri başlatmak ve durdurmak için komutlar

*ÖNEMLİ: Aşağıdaki komutların tümü idari ayrıcalıklar gerektirir.*

| Seçenek           | Bağımsız değişkenler ve açıklama |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | *Vcperf.exe'ye* verilen oturum adı altında iz bırakmasını söyler. Belirli bir makinede aynı anda yalnızca bir etkin oturum olabilir. <br/><br/> Seçenek `/nocpusampling` belirtilirse, *vcperf.exe* CPU örnekleri toplamaz. Windows Performans Çözümleyicisi'nde CPU Kullanımı (Örneklenmiş) görünümünün kullanılmasını engeller, ancak toplanan izleri küçültür. <br/><br/> İzleme ye başladıktan sonra *vcperf.exe* hemen geri döner. Olaylar, makinede çalışan tüm işlemler için sistem genelinde toplanır. Bu *vcperf.exe*çalıştırmak için kullanılan aynı komut istemi projenizi oluşturmak gerekmez anlamına gelir. Örneğin, projenizi Visual Studio'dan oluşturabilirsiniz. |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | Verilen oturum adı ile tanımlanan izlemeyi durdurur. Windows Performans Çözümleyicisi'nde (WPA) görüntülenebilir bir dosya oluşturmak için izleme üzerinde bir işlem sonrası adım çalıştırın. En iyi görüntüleme deneyimi için, C++ Build Insights eklentisini içeren WPA sürümünü kullanın. Daha fazla bilgi için [C++ Build Insights ile başlayın.](/cpp/build-insights/get-started-with-cpp-build-insights) Parametre, `<outputFile.etl>` çıktı dosyasının nerede kaydedilen yeri belirtir. |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | Verilen oturum adı ile tanımlanan izlemeyi durdurur ve belirtilen çıktı dosyasına ham, işlenmemiş verileri yazar. Ortaya çıkan dosyaWPA'da görüntülenmez. <br/><br/> `/stop` Komutla ilgili işlem sonrası adım bazen uzun olabilir. Bu işlem `/stopnoanalyze` sonrası adımı geciktirmek için komutu kullanabilirsiniz. Windows `/analyze` Performance Analyzer'da görüntülenebilir bir dosya oluşturmaya hazır olduğunuzda komutu kullanın. |

## <a name="miscellaneous-commands"></a>Çeşitli komutlar

| Seçenek     | Bağımsız değişkenler ve açıklama |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | Komut tarafından üretilen ham izleme `/stopnoanalyze` dosyasını kabul eder. Windows Performans Çözümleyicisi'nde görüntülenebilir bir dosya oluşturmak için bu izleme üzerinde bir işlem sonrası adım çalıştırın. En iyi görüntüleme deneyimi için, C++ Build Insights eklentisini içeren WPA sürümünü kullanın. Daha fazla bilgi için [C++ Build Insights ile başlayın.](/cpp/build-insights/get-started-with-cpp-build-insights) |

## <a name="see-also"></a>Ayrıca bkz.

[C++ Build Insights ile başlayın](/cpp/build-insights/get-started-with-cpp-build-insights)\
[Öğretici: Windows Performans Çözümleyicisi temelleri](/cpp/build-insights/tutorials/wpa-basics)\
[Başvuru: Windows Performans Çözümleyicisi görünümleri](wpa-views.md)\
[Windows Performans Analizörü](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end

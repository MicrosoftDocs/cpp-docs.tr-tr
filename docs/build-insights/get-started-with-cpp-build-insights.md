---
title: C++ Derleme İçgörüleri ile çalışmaya başlama
description: C++ derleme öngörülerine üst düzey bir genel bakış.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28d7e0758ea521af424129c546297fc97e3d6659
ms.sourcegitcommit: 8c8ed02a6f3bcb5ee008e3fe30ba7595d7c4c922
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83759231"
---
# <a name="get-started-with-c-build-insights"></a>C++ Derleme İçgörüleri ile çalışmaya başlama

::: moniker range="<=vs-2017"

C++ derleme öngörüleri araçları Visual Studio 2019 'de bulunabilir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

C++ derleme öngörüleri, Microsoft Visual C++ (MSVC) araç zinciri üzerinde daha fazla görünürlük sağlayan bir araç koleksiyonudur. Araçlar, C++ derlemelerinizi hakkında veri toplar ve bunu, yaygın soruları cevaplamanıza yardımcı olabilecek bir biçimde sunar:

- Derlemelerim yeterince paralelleştirildi mi?
- Önceden derlenmiş üst bilgiye (PCH) dahil ediyorum?
- Derleme hızlarımı artırmak için belirli bir darboğazın olması gerekir mi?

Bu teknolojinin ana bileşenleri şunlardır:

- derlemelerinizin izlemelerini toplamak için kullanabileceğiniz bir komut satırı yardımcı programı olan *vcperf. exe*,
- WPA 'da derleme izlemelerini görüntülemenize olanak tanıyan bir Windows Performans Çözümleyicisi (WPA) uzantısı ve
- C++ derleme öngörüleri verilerini kullanan kendi araçlarınızı oluşturmaya yönelik bir yazılım geliştirme seti olan C++ Build Insights SDK 'Sı.

## <a name="documentation-sections"></a>Belge bölümleri

[Öğretici: vcperf ve Windows Performans Çözümleyicisi](tutorials/vcperf-and-wpa.md)\
C++ projeleriniz için derleme izlemeleri toplamayı ve bunları WPA 'da görüntülemeyi öğrenin.

[Öğretici: Windows performansı temelleri](tutorials/wpa-basics.md)\
Derleme izlemelerinizi çözümlemek için kullanışlı WPA ipuçlarını bulun.

[C++ derleme öngörüleri SDK 'Sı](reference/sdk/overview.md)\
C++ Build Insights SDK 'sına genel bakış.

## <a name="articles"></a>Makaleler

C++ derleme öngörüleri hakkında daha fazla bilgi için resmi C++ ekip blogundan bu makaleleri okuyun:

[C++ derleme öngörülerini tanıtma](https://devblogs.microsoft.com/cppblog/introducing-c-build-insights/)

[C++ Build Insights SDK 'Sı ile derlemelerinizi programlı bir şekilde çözümleyin](https://devblogs.microsoft.com/cppblog/analyze-your-builds-programmatically-with-the-c-build-insights-sdk/)

[C++ derleme öngörüleri ile derleme darboğazlarını bulma](https://devblogs.microsoft.com/cppblog/finding-build-bottlenecks-with-cpp-build-insights/)

[C++ derleme öngörülerine yönelik PCH önerilerine sahip daha hızlı yapılar](https://devblogs.microsoft.com/cppblog/faster-builds-with-pch-suggestions-from-c-build-insights/)

::: moniker-end

---
title: C++ Derleme İçgörüleri ile çalışmaya başlama
description: Derleme öngörülerine yönelik C++ üst düzey bir genel bakış.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a5799fecc885b96f4278e0f5077662ce5fd7c8f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332013"
---
# <a name="get-started-with-c-build-insights"></a>C++ Derleme İçgörüleri ile çalışmaya başlama

::: moniker range="<=vs-2017"

Visual C++ Studio 2019 ' de derleme öngörüleri araçları mevcuttur. Bu sürümün belgelerini görmek için bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range="vs-2019"

C++Yapı öngörüleri, Microsoft Visual C++ (MSVC) araç zinciri üzerinde daha fazla görünürlük sağlayan bir araç koleksiyonudur. Araçlar derlemelerinizi C++ hakkında veri toplar ve bu bilgileri, şu gibi yaygın soruları cevaplamanıza yardımcı olabilecek bir biçimde sunar:

- Derlemelerim yeterince paralelleştirildi mi?
- Önceden derlenmiş üst bilgiye (PCH) dahil ediyorum?
- Derleme hızlarımı artırmak için belirli bir darboğazın olması gerekir mi?

Bu teknolojinin ana bileşenleri şunlardır:

- derlemelerinizin izlemelerini toplamak için kullanabileceğiniz bir komut satırı yardımcı programı olan *vcperf. exe*,
- WPA 'da derleme izlemelerini görüntülemenize olanak tanıyan bir Windows Performans Çözümleyicisi (WPA) uzantısı ve
- Yapı öngörüleri verilerini kullanan kendi araçlarınızı oluşturmaya yönelik bir yazılım geliştirme seti olan C++ Build Insights SDK 'sı. C++

Aşağıdaki bağlantılara tıklayarak bu bileşenleri hızlıca kullanmaya başlayın:

[Öğretici: vcperf ve Windows performans çözümleyicisi](tutorials/vcperf-and-wpa.md)\
C++ Projeleriniz için derleme izlemeleri toplamayı ve bunları WPA 'da görüntülemeyi öğrenin.

[Öğretici: Windows performans temelleri](tutorials/wpa-basics.md)\
Derleme izlemelerinizi çözümlemek için kullanışlı WPA ipuçlarını bulun.

Derleme öngörüleri SDK\ [ C++ ](reference/sdk/overview.md)
C++ Build Insights SDK 'sına genel bakış.

::: moniker-end

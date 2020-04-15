---
title: C++ Derleme İçgörüleri ile çalışmaya başlama
description: C++ Build Insights'a üst düzey bir genel bakış.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3a75dfe3bf1263cce53d70b764607cad4eec86d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325724"
---
# <a name="get-started-with-c-build-insights"></a>C++ Derleme İçgörüleri ile çalışmaya başlama

::: moniker range="<=vs-2017"

C++ Build Insights araçları Visual Studio 2019'da mevcuttur. Bu sürümün belgelerini görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

C++ Build Insights, Microsoft Visual C++ (MSVC) araç zincirinde daha fazla görünürlük sağlayan bir araç koleksiyonudur. Araçlar, C++ yapılarınız hakkında veri toplar ve aşağıdakiler gibi sık sorulan soruları yanıtlamanıza yardımcı olacak bir biçimde sunar:

- Yapılarımın yeterince paralelleştirilmiş mi?
- Önceden derlenmiş üstbilgime (PCH) ne eklemeliyim?
- Yapı hızlarımı artırmak için odaklanmam gereken belirli bir darboğaz var mı?

Bu teknolojinin ana bileşenleri şunlardır:

- *vcperf.exe*, yapılarınızın izlerini toplamak için kullanabileceğiniz bir komut satırı yardımcı programı,
- WPA'daki yapı izlerini görüntülemenizi sağlayan bir Windows Performans Çözümleyicisi (WPA) uzantısı ve
- C++ Build Insights SDK, C++ Build Insights verilerini tüketen kendi araçlarınızı oluşturmak için bir yazılım geliştirme kitidir.

Bu bileşenlerle hızlı bir şekilde başlamak için aşağıdaki linklere tıklayın:

[Öğretici: vcperf ve Windows Performans Analizörü](tutorials/vcperf-and-wpa.md)\
C++ projeleriniz için yapı izlerini nasıl topladığınızı ve bunları WPA'da nasıl görüntülenizi öğrenin.

[Öğretici: Windows Performans Temelleri](tutorials/wpa-basics.md)\
Yapı izlerinizi analiz etmek için yararlı WPA ipuçlarını keşfedin.

[C++ Build Insights SDK](reference/sdk/overview.md)\
C++ Build Insights SDK'ya genel bakış.

::: moniker-end

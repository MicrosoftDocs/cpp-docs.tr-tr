---
title: 'Öğretici: vcperf ve Windows Performans Analizörü'
description: C++ yapı izlerini analiz etmek için vcperf ve WPA'nın nasıl kullanılacağı hakkında öğretici.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c22f3dfddfd346d4f0eee898cb5164fd8923336e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323419"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>Öğretici: vcperf ve Windows Performans Analizörü

::: moniker range="<=vs-2017"

C++ Build Insights araçları Visual Studio 2019'da mevcuttur. Bu sürümün belgelerini görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

Bu eğitimde, C++ yapınızın izini toplamak için *vcperf.exe'yi* nasıl kullanacağınızı öğreneceksiniz. Bu izlemeyi Windows Performans Çözümleyicisi'nde nasıl görüntülediğinizi de öğreneceksiniz.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>Adım 1: Windows Performans Çözümleyicisi'ni yükleme ve yapılandırma

WPA, Windows Değerlendirme ve Dağıtım Kiti'nde (ADK) bulunan bir izleme görüntüleyicidir. Visual Studio yükleyicisiyle yükleyebileceğiniz bileşenlerin bir parçası olmayan ayrı bir yardımcı programdır.

C++ Build Insights'ı destekleyen WPA sürümü şu anda yalnızca Windows ADK Insider Preview'da kullanılabilir. Bu önizlemeye erişmek için Windows [Insider programına](https://insider.windows.com)kaydolmalısınız. Windows ADK önizlemesini elde etmek için Windows 10 Insider Preview işletim sistemini yüklemeniz gerekmez. Microsoft hesabınızı yalnızca Windows Insider Programı'na kaydetmeniz gerekir.

### <a name="to-download-and-install-wpa"></a>WPA'yı indirmek ve yüklemek için

NOT: Windows Performans Çözümleyicisini yüklemek için Windows 8 veya üzeri gereklidir.

1. Windows ADK Insider Preview [indirme sayfasına](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewADK)göz atın.

1. Windows ADK Insider Önizlemesini indirin. Bu bir disk görüntüsü.

1. Disk görüntüsünü açın ve *adksetup.exe* yükleyicisini çalıştırın.

1. Yüklemek istediğiniz özellikler için istendiğinde, Windows **Performance Toolkit'i**seçin. İsterseniz diğer özellikleri seçebilirsiniz, ancak WPA'yı yüklemeleri gerekmez.

   ![Windows Performans Çözümleyicisi yükleyicinin özellik seçim ekranı](media/wpa-installation.png)

### <a name="to-configure-build-insights"></a><a name="configuration-steps"></a>Yapı Öngörüleri yapılandırmak için

1. WPA'yı başlatın.

1. **Pencere** > **Seç Tabloları 'ni seçin (Deneme)**.

1. **Tanılama** bölümüne gidin.

1. Tüm MSVC Build Insights görünümlerini seçin.

   ![Windows Performans Çözümleyicisi tablo seçim paneli](media/wpa-configuration.png)

## <a name="step-2-trace-your-build-with-vcperfexe"></a>Adım 2: vcperf.exe ile yapınızı takip edin

C++ Build Insights verilerini görüntülemek için önce aşağıdaki adımları izleyerek bir izleme dosyasında toplayın:

1. Yönetici modunda Visual Studio 2019 için yerel araçlar veya çapraz araçlar geliştirici komut istemi açın. (Başlat menüsü öğesini sağ tıklatın ve yönetici olarak **Daha Fazla** > **Çalıştır'ı**seçin.)

1. Komut istemi penceresinde, şu komutu girin:

   **vcperf.exe /başlangıç _SessionName_**

   *SessionName*için hatırlayacağınız bir oturum adı seçin.

1. Projenizi normalde yaptığınız gibi oluşturun. Oluşturmak için aynı komut istemi penceresini kullanmanız gerekmez.

1. Komut istemi penceresinde, şu komutu girin:

   **vcperf.exe /stop _SessionName_ _traceFile.etl_**

   *SessionName* için daha önce seçtiğiniz oturum adını kullanın. *traceFile.etl* trace dosyası için uygun bir ad seçin.

Tipik bir *vcperf.exe* komut dizisi geliştirici komut istemi penceresinde şu şekilde görünür:

![Basit bir vcperf.exe kullanım senaryosu](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>vcperf.exe hakkında önemli notlar

- Yönetici ayrıcalıkları başlatmak veya bir *vcperf.exe* izleme durdurmak için gereklidir. **Çalıştır'ı yönetici olarak**kullanarak açtığınız geliştirici komut istemi pencereni kullanın.

- Bir makinede aynı anda yalnızca bir izleme oturumu çalışabilir.

- İzlemenizi başlatmak için kullandığınız oturum adını hatırladığınızdan emin olun. Adını bilmeden çalışan bir oturumu durdurmak zahmetli olabilir.

- Cl.exe ve *link.exe*gibi, komut satırı programı *vcperf.exe* bir MSVC yükleme dahildir. *cl.exe* Bu bileşeni elde etmek için ek adım gerekmez.

- *vcperf.exe* sisteminizde çalışan tüm MSVC araçları hakkında bilgi toplar. Sonuç olarak, izlemeyi toplamak için kullandığınız komut isteminden yapınızı başlatmanız gerekmez. Projenizi farklı bir komut isteminden veya Visual Studio'dan oluşturabilirsiniz.

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>Adım 3: Windows Performans Çözümleyicisi'nde izinizi görüntüleyin

WPA'yı başlatın ve az önce topladığınız izi açın. WPA bunu c++ Build Insights izleme olarak tanımalı ve soldaki Grafik Gezgini panelinde aşağıdaki görünümler görünmelidir:

- Explorer oluştur
- Dosyalar
- İşlev

Bu görünümleri göremiyorsanız, [Adım 1'de](#configuration-steps)açıklandığı gibi WPA'nın doğru şekilde yapılandırıldığından iki kez denetleyin. Görünümleri sağdaki boş Çözümleme penceresine sürükleyerek yapı verilerinizi görüntüleyebilirsiniz:

![Windows Performans Çözümleyicisinde C++ Yapı Öngörüleri izleme](media/wpa-viewing-trace.gif)

Diğer görünümler Graph Explorer panelinde mevcuttur. İçerdikleri bilgilerle ilgilendiğinizde bunları Çözümleme penceresine sürükleyin. Yararlı bir CPU (Örneklenmiş) görünümü, yapı boyunca CPU kullanımını gösterir.

## <a name="more-information"></a>Daha fazla bilgi

[Öğretici: Windows Performans Çözümleyicisi temelleri](wpa-basics.md)\
Yapı izlemelerinizi çözümlemenize yardımcı olabilecek yaygın WPA işlemleri hakkında bilgi edinin.

[Referans: vcperf komutları](/cpp/build-insights/reference/vcperf-commands)\
*Vcperf.exe* komut başvurusu tüm kullanılabilir komut seçeneklerini listeler.

[Başvuru: Windows Performans Çözümleyicisi görünümleri](/cpp/build-insights/reference/wpa-views)\
WPA'daki C++ Build Insights görünümleri hakkında ayrıntılar için bu makaleye bakın.

[Windows Performans Analizörü](/windows-hardware/test/wpt/windows-performance-analyzer)\
Resmi WPA dokümantasyon sitesi.

::: moniker-end

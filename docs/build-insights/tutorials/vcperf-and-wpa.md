---
title: 'Öğretici: vcperf ve Windows Performans Çözümleyicisi'
description: Bkz. vcperf ve WPA 'Yı C++ derleme izlemelerinin çözümlenmesi için kullanma öğreticisi.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b82c1f7105b3fd03d8c21dd79617dbc66f3e090c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507773"
---
# <a name="tutorial-vcperf-and-windows-performance-analyzer"></a>Öğretici: vcperf ve Windows Performans Çözümleyicisi

::: moniker range="<=vs-2017"

C++ derleme öngörüleri araçları Visual Studio 2019 'de bulunabilir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range="vs-2019"

Bu öğreticide, C++ yapınızı izlemeyi toplamak için *vcperf.exe* kullanmayı öğreneceksiniz. Ayrıca, bu izlemeyi Windows Performans Çözümleyicisi 'nde görüntülemeyi de öğreneceksiniz.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>1. Adım: Windows Performans Çözümleyicisi 'ni yükleyip yapılandırma

WPA, Windows değerlendirme ve dağıtım seti 'nde (ADK) bulunan bir izleme görüntüleyicisine sahiptir. Visual Studio yükleyicisi ile yükleyebileceğiniz bileşenlerin parçası olmayan ayrı bir yardımcı programdır.

C++ derleme öngörülerini destekleyen bir WPA sürümü şu anda yalnızca Windows ADK Insider Preview 'da bulunabilir. Bu önizlemeye erişmek için [Windows Insider programına](https://insider.windows.com)kaydolmanız gerekir. Windows ADK önizlemesi 'ni edinmek için Windows 10 Insider Preview işletim sistemini yüklemeniz gerekmez. Yalnızca Microsoft hesabı Windows Insider programı ile kaydetmeniz gerekir.

### <a name="to-download-and-install-wpa"></a>WPA 'Yı indirmek ve yüklemek için

NOTE: Windows Performans Çözümleyicisi 'ni yüklemek için Windows 8 veya üzeri gereklidir.

1. Windows ADK [indirme sayfasına](/windows-hardware/get-started/adk-install)gidin.

1. Windows ADK 'nin en son sürümünü indirip yükleyin.

1. Yüklemek istediğiniz özellikler istendiğinde, **Windows performans araç seti**' ni seçin. İsterseniz diğer özellikleri seçebilirsiniz, ancak WPA 'Yı yüklemek gerekli değildir.

   ![Windows Performans Çözümleyicisi yükleyicisi 'nin Özellik seçimi ekranı](media/wpa-installation.png)

### <a name="to-configure-wpa"></a><a name="configuration-steps"></a> WPA 'Yı yapılandırmak için

WPA 'da C++ derleme öngörülerini görüntüleme özel bir eklenti gerektirir. Yüklemek için aşağıdaki adımları izleyin:

1. Aşağıdaki bileşenlerden birini indirerek eklentiyi edinin. Her ikisini de almanız gerekmez. En uygun bulduğunuz birini seçin.
    1. [Visual Studio 2019 sürüm 16,6 ve üzeri](https://visualstudio.microsoft.com/downloads/), ya da
    1. [C++ derleme öngörüleri NuGet paketi](https://www.nuget.org/packages/Microsoft.Cpp.BuildInsights/).

1. `perf_msvcbuildinsights.dll`Dosyayı WPA yükleme dizininize kopyalayın.
    1. Visual Studio 2019 sürüm 16,6 ve üzeri sürümlerde, bu dosya şurada bulunur: `C:\Program Files (x86)\Microsoft Visual Studio\2019\{Edition}\VC\Tools\MSVC\{Version}\bin\Host{Architecture}\{Architecture}` .
    1. C++ derleme öngörüleri NuGet paketinde bu dosya şurada bulunur: `wpa\{Architecture}` .
    1. Yukarıdaki yollarda, küme ayraçları ile çevrelenen değişkenleri aşağıdaki gibi değiştirin:
        1. `{Edition}` Community, Professional veya Enterprise gibi Visual Studio 2019 sürümünüz.
        1. `{Version}` MSVC sürümdür. Kullanılabilir en yüksek olanı seçin.
        1. `{Architecture}`: `x64` Windows 'un 64 bit sürümüne sahip olup olmadığını seçin. Aksi takdirde, öğesini seçin `x86` .
    1. WPA yükleme dizini genellikle: `C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit` .

1. WPA yükleme dizininizde, `perfcore.ini` dosyasını açın ve için bir giriş ekleyin `perf_msvcbuildinsights.dll` .

## <a name="step-2-trace-your-build-with-vcperfexe"></a>2. Adım: vcperf.exe yapınızı Izleme

C++ derleme öngörüleri verilerini görüntülemek için, önce aşağıdaki adımları izleyerek bir izleme dosyasında toplayın:

1. Yönetici modunda **VS 2019 için** bir **x64** veya x86 yerel araçları komut istemi açın. (Başlat menüsü öğesine sağ tıklayıp **daha fazla**  >  öğesini seçin **Yönetici olarak çalıştır**.)
    1. Windows 'un 64 bit sürümüne sahipseniz **x64** seçeneğini belirleyin. Aksi takdirde, **x86**' yı seçin.

1. Komut istemi penceresinde şu komutu girin:

   **vcperf.exe/Start _oturumadı_**

   *Oturumadı*için hatırlayacaksınız bir oturum adı seçin.

1. Projenizi normalde yaptığınız şekilde derleyin. Derlemek için aynı komut istemi penceresini kullanmanız gerekmez.

1. Komut istemi penceresinde şu komutu girin:

   **vcperf.exe/Stop _oturumadı_ _TraceFile. etl_**

   Daha önce *oturumadı* için seçtiğiniz oturum adını kullanın. *TraceFile. etl* trace dosyası için uygun bir ad seçin.

Bir geliştirici komut istemi penceresinde, tipik bir *vcperf.exe* komut sırası şöyle görünür:

![Basit bir vcperf.exe kullanımı senaryosu](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>vcperf.exe hakkındaki önemli notlar

- *vcperf.exe* izlemesini başlatmak veya durdurmak için yönetici ayrıcalıkları gerekir. **Yönetici olarak çalıştır**'ı kullanarak açtığınız bir geliştirici komut istemi penceresi kullanın.

- Bir makinede tek seferde yalnızca bir izleme oturumu çalıştırılabilir.

- İzlemeyi başlatmak için kullandığınız oturum adını unutduğunuzdan emin olun. Bir çalışan oturumu adını bilmeden durdurmak için sorunlu olabilir.

- *cl.exe* ve *link.exe*gibi, komut satırı YARDıMCı programı *vcperf.exe* bir MSVC yüklemesine dahil edilmiştir. Bu bileşeni edinmek için ek adım gerekmez.

- *vcperf.exe* sisteminizde çalışan tüm MSVC araçları hakkında bilgi toplar. Sonuç olarak, derlemenizi, izlemeyi toplamak için kullandığınız komut isteminden başlatmanız gerekmez. Projenizi farklı bir komut isteminden ya da Visual Studio 'da oluşturabilirsiniz.

### <a name="vcperfexe-is-open-source"></a>vcperf.exe açık kaynak

Kendi *vcperf.exe*sürümünüzü oluşturmak ve çalıştırmak istiyorsanız, bunu [vcperf GitHub deposundan](https://github.com/microsoft/vcperf)klonlayın.

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>3. Adım: Windows Performans Çözümleyicisi 'nde izlemenizi görüntüleme

WPA 'Yı başlatın ve yeni topladığınız izlemeyi açın. WPA bunu bir C++ Build Insights izlemesi olarak tanıması gerekir ve sol taraftaki grafik Gezgini panelinde aşağıdaki görünümler görünmelidir:

- Yapı Gezgini
- Dosyalar
- İşlevler
- Şablon örneklemeleri

Bu görünümleri göremiyorsanız, [1. adım](#configuration-steps)bölümünde açıklandığı gıbı, WPA 'nın doğru şekilde yapılandırıldığından emin olun. Aşağıdaki şekilde gösterildiği gibi, görünümleri sağ taraftaki boş analiz penceresine sürükleyerek yapı verilerinizi görüntüleyebilirsiniz:

![Windows Performans Çözümleyicisi 'nde C++ derleme öngörüleri izlemesini görüntüleme](media/wpa-viewing-trace.gif)

Grafik Gezgini panelinde diğer görünümler de mevcuttur. İçerdikleri bilgilerle ilgileniyor olduğunuzda bunları analiz penceresine sürükleyin. Yararlı bir tane, derleme genelinde CPU kullanımını gösteren CPU (örneklenmiş) görünümüdür.

## <a name="more-information"></a>Daha fazla bilgi

[Öğretici: Windows Performans Çözümleyicisi temelleri](wpa-basics.md)\
Derleme izlemelerinizi çözümlemenize yardımcı olabilecek genel WPA işlemleri hakkında bilgi edinin.

[Reference: vcperf komutları](../reference/vcperf-commands.md)\
*vcperf.exe* komut başvurusu, kullanılabilir tüm komut seçeneklerini listeler.

[Başvuru: Windows Performans Çözümleyici görünümleri](../reference/wpa-views.md)\
WPA 'daki C++ derleme öngörüleri görünümleri hakkında daha fazla bilgi için bu makaleye bakın.

[Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)\
Resmi WPA belge sitesi.

::: moniker-end

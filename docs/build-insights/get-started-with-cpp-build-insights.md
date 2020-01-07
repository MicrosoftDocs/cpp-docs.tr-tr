---
title: C++ Derleme İçgörüleri ile çalışmaya başlama
description: C++ Derleme öngörülerinin parçası olan derleme zamanı performans analizi araçlarının nasıl kullanılacağına ilişkin üst düzey bir genel bakış.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 862bfae3bdb27812306dcd356aecab812ea5181c
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298746"
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

Bu teknolojinin iki ana bileşeni, Windows Performans Çözümleyicisi (WPA) izleme görüntüleyicisinin komut satırı yardımcı programıdır *vcperf. exe* ve bir eklentidir. Bu yardımcı program, yapılarınızın izlemelerini toplamak için kullanılır, ancak eklenti bunları WPA 'da görüntülemenize izin verir. Bu iki aracı kullanmaya başlamak için bu adımları izleyin.

## <a name="step-1-install-and-configure-windows-performance-analyzer"></a>1\. Adım: Windows Performans Çözümleyicisi 'ni yükleyip yapılandırma

WPA, Windows değerlendirme ve dağıtım seti 'nde (ADK) bulunan bir izleme görüntüleyicisine sahiptir. Visual Studio yükleyicisi ile yükleyebileceğiniz bileşenlerin parçası olmayan ayrı bir yardımcı programdır.

Derleme öngörülerini destekleyen C++ bir WPA sürümü şu anda yalnızca Windows ADK Insider Preview 'da bulunabilir. Bu önizlemeye erişmek için [Windows Insider programına](https://insider.windows.com)kaydolmanız gerekir. Windows ADK önizlemesi 'ni edinmek için Windows 10 Insider Preview işletim sistemini yüklemeniz gerekmez. Yalnızca Microsoft hesabı Windows Insider programı ile kaydetmeniz gerekir.

### <a name="to-download-and-install-wpa"></a>WPA 'Yı indirmek ve yüklemek için

NOTE: Windows Performans Çözümleyicisi 'ni yüklemek için Windows 8 veya üzeri gereklidir.

1. Windows ADK Insider Önizleme [indirme sayfasına](https://www.microsoft.com/en-us/software-download/windowsinsiderpreviewADK)gidin.

1. Windows ADK Insider Preview ' i indirin. Bu bir disk görüntüsüdür.

1. Disk görüntüsünü açın ve *adksetup. exe* yükleyicisini çalıştırın.

1. Yüklemek istediğiniz özellikler istendiğinde, **Windows performans araç seti**' ni seçin. İsterseniz diğer özellikleri seçebilirsiniz, ancak WPA 'Yı yüklemek gerekli değildir.

   ![Windows Performans Çözümleyicisi yükleyicisi 'nin Özellik seçimi ekranı](media/wpa-installation.png)

### <a name="configuration-steps"></a>Derleme öngörülerini yapılandırmak için

1. WPA 'Yı başlatın.

1. **Tablo seç > (deneysel)** **pencere** seçin.

1. Aşağı kaydırarak **Tanılama** bölümüne gidin.

1. Tüm MSVC Build Insights görünümlerini seçin.

   ![Windows Performans Çözümleyicisi 'nin tablo seçim paneli](media/wpa-configuration.png)

## <a name="step-2-trace-your-build-with-vcperfexe"></a>2\. Adım: vcperf. exe ile derlemenizi Izleme

Build Insights C++ verilerini görüntülemek için, önce aşağıdaki adımları izleyerek bunu bir izleme dosyasına toplayın:

1. Yönetici modunda Visual Studio 2019 için yerel araçlar veya çapraz Araçlar Geliştirici komut istemi 'ni açın. (Başlat menüsü öğesine sağ tıklayın ve **yönetici olarak çalıştır** > **diğer** ' i seçin.)

1. Komut istemi penceresinde şu komutu girin:

   **vcperf. exe/Start _oturumadı_**

   *Oturumadı*için hatırlayacaksınız bir oturum adı seçin.

1. Projenizi normalde yaptığınız şekilde derleyin. Derlemek için aynı komut istemi penceresini kullanmanız gerekmez.

1. Komut istemi penceresinde şu komutu girin:

   **vcperf. exe/Stop _oturumadı_ _TraceFile. etl_**

   Daha önce *oturumadı* için seçtiğiniz oturum adını kullanın. *TraceFile. etl* trace dosyası için uygun bir ad seçin.

Tipik bir *vcperf. exe* komut sırası, geliştirici komut istemi penceresinde şöyle görünür:

![Basit bir vcperf. exe kullanım senaryosu](media/vcperf-simple-usage.png)

### <a name="important-notes-about-vcperfexe"></a>Vcperf. exe hakkında önemli notlar

- Bir *vcperf. exe* izlemesini başlatmak veya durdurmak için yönetici ayrıcalıkları gerekir. **Yönetici olarak çalıştır**'ı kullanarak açtığınız bir geliştirici komut istemi penceresi kullanın.

- Bir makinede tek seferde yalnızca bir izleme oturumu çalıştırılabilir.

- İzlemeyi başlatmak için kullandığınız oturum adını unutduğunuzdan emin olun. Bir çalışan oturumu adını bilmeden durdurmak için sorunlu olabilir.

- Yalnızca *CL. exe* ve *LINK. exe*gibi komut satırı yardımcı programı *VCPERF. exe* bir MSVC yüklemesinde bulunur. Bu bileşeni edinmek için ek adım gerekmez.

- *vcperf. exe* , sisteminizde çalışan tüm MSVC araçları hakkında bilgi toplar. Sonuç olarak, derlemenizi, izlemeyi toplamak için kullandığınız komut isteminden başlatmanız gerekmez. Projenizi farklı bir komut isteminden ya da Visual Studio 'da oluşturabilirsiniz.

## <a name="step-3-view-your-trace-in-windows-performance-analyzer"></a>3\. Adım: Windows Performans Çözümleyicisi 'nde izlemenizi görüntüleme

WPA 'Yı başlatın ve yeni topladığınız izlemeyi açın. WPA bunu bir C++ Build Insights izlemesi olarak tanıması gerekir ve sol taraftaki grafik Gezgini panelinde aşağıdaki görünümler görünmelidir:

- Derleme Gezgini
- Dosyalar
- İşlev

Bu görünümleri göremiyorsanız, [1. adım](#configuration-steps)bölümünde açıklandığı gıbı, WPA 'nın doğru şekilde yapılandırıldığından emin olun. Aşağıdaki şekilde gösterildiği gibi, görünümleri sağ taraftaki boş analiz penceresine sürükleyerek yapı verilerinizi görüntüleyebilirsiniz:

![Windows performans C++ Çözümleyicisi 'nde bir Build Insights izlemesini görüntüleme](media/wpa-viewing-trace.gif)

Grafik Gezgini panelinde diğer görünümler de mevcuttur. İçerdikleri bilgilerle ilgileniyor olduğunuzda bunları analiz penceresine sürükleyin. Yararlı bir tane, derleme genelinde CPU kullanımını gösteren CPU (örneklenmiş) görünümüdür.

## <a name="more-information"></a>Daha fazla bilgi

[Windows Performans Çözümleyici temelleri](wpa-basics.md)\
Derleme izlemelerinizi çözümlemenize yardımcı olabilecek genel WPA işlemleri hakkında bilgi edinin.

[vcperf. exe başvuru](vcperf-reference.md)\
*Vcperf. exe* komut başvurusu, kullanılabilir tüm komut seçeneklerini listeler.

[Windows Performans Çözümleyici görünümleri başvuru](wpa-views-reference.md)\
WPA 'daki C++ derleme öngörüleri görünümleri hakkında daha fazla bilgi için bu makaleye bakın.

[Windows performans çözümleyici](/windows-hardware/test/wpt/windows-performance-analyzer)\
Resmi WPA belge sitesi.

::: moniker-end

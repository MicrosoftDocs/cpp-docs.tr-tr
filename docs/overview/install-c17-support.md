---
title: Visual Studio 'da C11 ve C17 desteğini yükler
description: Visual Studio 'da C11 ve C17 için Windows SDK ve CRT desteğini yükleyip
ms.date: 09/11/2020
helpviewer_keywords:
- Install preview Windows SDK
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 86de38feb66ab0a057005140d22cf0dd3b03d4cf
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079124"
---
# <a name="install-c11-and-c17-support-in-visual-studio"></a>Visual Studio 'da C11 ve C17 desteğini yükler

::: moniker range="<=vs-2017"

C11 ve C17 standartları için destek, Visual Studio 2019 sürüm 16,8 veya üstünü gerektirir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range="vs-2019"

C11 ve C17 standartlarına yönelik destek, Visual Studio 2019 sürüm 16,8 ' den başlayarak kullanılabilir. Destek, güncelleştirilmiş bir Universal C çalışma zamanı (UCRT) ve en son Windows SDK güncelleştirmelerinin, uyumlu Önişlemci () ile düzgün şekilde çalışmasını gerektirir [`/Zc:preprocessor`](../build/reference/zc-preprocessor.md) .

Windows SDK sürümleri, Windows işletim sistemi yayınlarına karşılık gelir. Bu değişikliklerle bir Windows sürümü olmadığından, bir *Insider preview Windows SDK*gerekir. Bu, Windows Insider 'lar tarafından şu anda yük *almakta olan veya sınanmış olan Windows*derlemeleriyle ilgili Windows SDK önizleme sürümüdür. Insider Preview Windows 10 SDK 'sını yükledikten sonra, en son Windows SDK kullanacak şekilde yapılandırılmış Visual Studio projeleri Insider Preview 'ı kullanacaktır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2019 sürüm 16,8 Preview 3 veya sonraki sürümleri bilgisayarınızda yüklü ve çalışır. Yüklemede, C++ iş yüküyle masaüstü geliştirmeyi dahil edin. [Visual Studio önizleme](https://visualstudio.microsoft.com/vs/preview/) sayfasından en son önizlemeyi indirebilirsiniz. Visual Studio henüz yüklenmemişse yükleme yönergeleri için [Visual Studio 'Da C++ desteğini yükleme](../build/vscpp-step-0-installation.md) makalesine bakın.

## <a name="step-1-sign-in-by-using-an-insider-microsoft-account"></a>1. Adım: Insider Microsoft hesabı kullanarak oturum açın

Herkes ücretsiz bir [Microsoft hesabı](https://signup.live.com/) oluşturup Insider programını kabul edebilir. [Geliştiriciler Için Windows Insider programı](https://insider.windows.com/for-developers) sayfasına gidin, **Kaydet**' i seçin ve oturum açın.

Kaydolduktan sonra Windows 'un fışıklandırma Insider sürümlerini başlatma seçeneği sunulur. Bu adım, Insider Windows 10 SDK 'sını indirmek ve kullanmak için gerekli değildir. Windows Insider 'a kaydoldığınızda, yeni Windows fışıklarınızı indirmek için makinelerinizi otomatik olarak kabul etmez.

**Windows Insider programı 'Na hoş geldiniz** sayfasına geldiğinizde **Şimdi uçuş**' ı seçmeniz gerekmez. Insider Preview Windows 10 SDK 'sını indirmek için sonraki adıma geçin.

## <a name="step-2-download-the-insider-preview-windows-10-sdk"></a>2. Adım: Insider Preview Windows 10 SDK 'sını Indirin

[Windows Insider Preview İndirmeleri](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK) sayfasından ınsider Preview Windows SDK yükleyebilirsiniz. "Windows Insider programının bir üyesi olmanız gerekir" iletisini görürseniz, oturum açtığınızdan emin olun. Insider programı için kullandığınız Microsoft hesabı aynısını kullanın. "Üzgünüz, istediğiniz sayfa bulunamıyor" iletisini görürseniz, URL 'deki yerel ayarı *en-US*olarak değiştirmeyi deneyin.

Windows 10 Insider Preview işletim sistemi kullanan Insider Page talepleri gereklidir. Yalnızca Windows SDK eklenen bazı içerikler için geçerlidir. Bu içerik, Windows 'un eski sürümlerinde mevcut olmayan yeni API 'Lere bağlı olabilir. Ancak, Windows ve evrensel C çalışma zamanı üst bilgileri, bir Insider OS olmadan yükleyebilir ve kullanılabilir.

İndirmeye başlamak için **SDK Insider Preview 'ı al – derleme 20211** (veya üzeri) seçeneğini belirleyin. Windows SDK sonraki sürümleri de çalışacaktır.

## <a name="step-3-install-the-insider-preview-windows-10-sdk"></a>3. Adım: Insider Preview Windows 10 SDK 'sını yükler

Insider Preview Windows SDK dosya olarak indirilir *`.iso`* . Dosya Gezgini 'nde indirilen dosyayı içeren klasörü açın. Dosyayı bağlayın *`.iso`* ve sonra *`WinSDKSetup.exe`* yüklemeyi başlatmak için öğesini çalıştırın.

**Konum belirt** sayfasında, **Windows yazılım geliştirme seti 'Ni \<version> Bu bilgisayara yükleyip** **İleri**' yi seçin. **Windows setleri gizlilik** sayfasında, Microsoft 'un Windows 10 takımları için öngörüleri toplamasına izin verip vermeyeceğinizi seçip **İleri**' yi seçin. Lisans sözleşmesini kabul etmek için **kabul et** ' i seçin. Yüklemek istediğiniz **özellikleri seçin** sayfasında, yalnızca şu özellikleri seçin:  

- Masaüstü uygulamaları için Windows SDK Imzalama araçları

- UWP tarafından yönetilen uygulamalar için Windows SDK

- UWP C++ uygulamaları için Windows SDK

- Masaüstü C++ x86 uygulamaları için Windows SDK (x86 için derlemeyi planlıyorsanız)

- Masaüstü C++ AMD64 uygulamaları için Windows SDK (AMD64 için derlemeyi planlıyorsanız)

- Masaüstü C++ ARM uygulamaları için Windows SDK (ARM için derlemeyi planlıyorsanız)

- Masaüstü C++ arm64 uygulamaları için Windows SDK (arm64 için derlemeyi planlıyorsanız)

![Yükleme için seçilen bileşenleri gösteren Windows SDK yükleyicisinin ekran görüntüsü](media/c11-7-windows-sdk-installer-select-features.png)

Seçili SDK bileşenlerini yüklemek için **yüklemeyi** seçin. SDK 'nın yüklemeyi tamamlaması birkaç dakika sürer. Tamamlandığında, Visual Studio 'Yu açın.

## <a name="step-4-configuring-c11-or-c17-mode-in-visual-studio"></a>4. Adım: Visual Studio 'da C11 veya C17 modunu yapılandırma

Visual Studio 'da, yeni veya mevcut bir C projesi açın, sonra projenizin **Özellik sayfaları** iletişim kutusunu açın.

Projeyi Insiders Önizleme Windows 10 SDK 'sını kullanacak şekilde ayarlayın. **Yapılandırma özellikleri**  >  **genel** sayfasında, **Windows SDK Version** özelliğini **10,0 (en son yüklenen sürüm)** ya da yüklediğiniz belirli bir önizleme sürümü olarak ayarlayın.

Ayrıca yeni bir seçenek görürsünüz: **C dil standardı**. Bu özelliği **ISO C11 Standard ( `/std:c11` )** veya **ISO C17 (2018) standardı ( `/std:c17` )** olarak ayarlayın.  

![Yapılandırma Özellikleri Genel sayfasındaki özellik sayfaları iletişim kutusunun bir ekran görüntüsü, C dili standart özelliği açılan listesini ISO C 17 olarak gösterir](media/c11-9-project-property-page-c-language-standard.png)

C++ dil standardı, dil C++ olduğunda kullanılır. Dosya uzantısı olduğunda varsayılandır *`.cpp`* . Dil C olduğunda C dili standart sürümü kullanılır. Dosya uzantısı olduğunda varsayılandır *`.c`* . C11 veya C17 kullanarak derlemek için, kaynak kodunuzu bir *`.c`* dosyaya koyun veya kodu C olarak derle olarak ayarlayın. Projeniz için bu özelliği, **yapılandırma özellikleri**  >  **C/C++**  >  **Gelişmiş** sayfasında ayarlayabilirsiniz. **Derleme olarak derle** özelliğini **C kodu olarak derle (/TC)** olarak ayarlayın.

Tebrikler, Visual Studio 2019 sürüm 16,8 Preview 3 ' te C11 ve C17 Code derlemek için gereken her şeyi ayarlamış olursunuz!

## <a name="see-also"></a>Ayrıca bkz.

[`/std` (Dil standart sürümünü belirt)](../build/reference/std-specify-language-standard-version.md)

::: moniker-end

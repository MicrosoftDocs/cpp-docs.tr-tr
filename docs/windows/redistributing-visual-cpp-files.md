---
title: Visual C++ Dosyalarını Yeniden Dağıtma
description: Visual Studio, uygulamanızla birlikte dağıtabileceğiniz yeniden dağıtılabilir kitaplıkları ve bileşenleri içerir.
ms.date: 07/16/2020
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
ms.openlocfilehash: 7a639f7ad7deb76cade47b0162012dcb70cb0d69
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446759"
---
# <a name="redistributing-visual-c-files"></a>Visual C++ Dosyalarını Yeniden Dağıtma

> [!NOTE]
> İşte Visual C++ çalışma zamanı dosyalarından birinin İndiriyor musunuz? [Microsoft Web sitesine](https://www.microsoft.com/) gidin ve arama kutusuna **Visual C++ yeniden dağıtılabilir** girin. Bilgisayarınızın mimarisine yönelik yeniden dağıtılabilir paketi (örneğin, 64 bit Windows çalıştırıyorsanız x64) ve ihtiyacınız olan Visual C++ (örneğin, 2015) sürümünü indirip yükleyin.

## <a name="redistributable-files-and-licensing"></a>Yeniden dağıtılabilir dosyalar ve lisanslama

Bir uygulamayı dağıtırken, onu desteklemek için gerekli tüm dosyaları da dağıtmalısınız. Bu dosyalardan herhangi biri Microsoft tarafından sağlandıysa, bunları yeniden dağıtmanıza izin verilip verilmeyeceğini kontrol edin. IDE 'deki Visual Studio lisans koşullarına bir bağlantı bulacaksınız. Hakkında Microsoft Visual Studio iletişim kutusunda lisans koşulları bağlantısını kullanın. Ya da, ilgili EULA 'Ları ve lisansları Visual Studio [Lisans dizininden](https://visualstudio.microsoft.com/license-terms/)indirebilirsiniz.

::: moniker range="vs-2019"

Visual Studio 2019 Microsoft yazılımı lisans koşullarının "dağıtılabilir kod" bölümünde başvurulan "REDıST listesi" ni görüntülemek için bkz. [Microsoft Visual Studio 2019 Için dağıtılabilir kod dosyaları](/visualstudio/releases/2019/redistribution#-distributable-code-files-for-visual-studio-2019)

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 Microsoft yazılımı lisans koşullarının "dağıtılabilir kod" bölümünde başvurulan "REDıST listesi" ni görüntülemek için, bkz. [Microsoft Visual Studio 2017 Için dağıtılabilir kod dosyaları](/visualstudio/productinfo/2017-redistribution-vs#-distributable-code-files-for-visual-studio-2017).

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015 Microsoft yazılımı lisans koşullarının "dağıtılabilir kod" bölümünde başvurulan "REDıST listesi" ni görüntülemek için, bkz. [Microsoft Visual Studio 2015 Için dağıtılabilir kod dosyaları](/visualstudio/productinfo/2015-redistribution-vs#-distributable-code-files-for-visual-studio-2015).

::: moniker-end

Yeniden dağıtılabilir dosyalar hakkında daha fazla bilgi için bkz. [hangi dll 'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md) ve [dağıtım örneklerini](deployment-examples.md)belirleme.

## <a name="locate-the-redistributable-files"></a>Yeniden dağıtılabilir dosyaları bulma

Yeniden dağıtılabilir dosyaları dağıtmak için, Visual Studio tarafından yüklenen yeniden dağıtılabilir paketleri kullanabilirsiniz. Visual Studio 'nun 2017 sonrasındaki sürümlerinde, bu dosyalar ve olarak adlandırılır *`vc_redist.arm64.exe`* *`vc_redist.x64.exe`* *`vc_redist.x86.exe`* . Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 ' de,, *`vcredist_x86.exe`* *`vcredist_x64.exe`* ve *`vcredist_arm.exe`* (yalnızca 2015) adlarında de mevcuttur.

Yeniden dağıtılabilir dosyaları bulmanın en kolay yolu, bir geliştirici komut isteminde ayarlanan ortam değişkenlerini kullanmaktır. Visual Studio 2019 ' nin en son sürümünde, yeniden dağıtılabilir dosyaları *`%VCINSTALLDIR%Redist\MSVC\v142`* klasöründe bulabilirsiniz. Hem Visual Studio 2017 hem de Visual Studio 2019 ' de de bulunur *`%VCToolsRedistDir%`* . Visual Studio 2015 ' de, bu dosyalar ' de bulunabilir; *`%VCINSTALLDIR%redist\<locale>`* burada *`<locale>`* yeniden dağıtılabilir paketlerin yerel ayarıdır.

Başka bir dağıtım seçeneği, yeniden dağıtılabilir birleştirme modüllerini ( *`.msm`* Dosyalar) kullanmaktır. Visual Studio 2019 ' de bu dosyalar, Visual Studio Yükleyicisi **C++ 2019 Redistributable MSMs** adlı isteğe bağlı bir yüklenebilir bileşenin parçasıdır. Birleştirme modülleri, Visual Studio 2017 ve Visual Studio 2015 ' deki bir C++ yüklemesinin parçası olarak varsayılan olarak yüklenir. Visual Studio 2019 ' nin en son sürümünde yüklendiğinde, yeniden dağıtılabilir birleştirme modüllerini ' de bulacaksınız *`%VCINSTALLDIR%Redist\MSVC\v142\MergeModules`* . Hem Visual Studio 2019 hem de Visual Studio 2017 ' de de bulunur *`%VCToolsRedistDir%MergeModules`* . Visual Studio 2015 ' de, içinde bulunur *`Program Files [(x86)]\Common Files\Merge Modules`* .

## <a name="install-the-redistributable-packages"></a>Yeniden dağıtılabilir paketleri yükler

Visual C++ Yeniden Dağıtılabilir Paketleri tüm Visual C++ kitaplıklarını yükler ve kaydeder. Kullanıyorsanız, uygulamanızı yüklemeden önce hedef sistemde bir önkoşul olarak çalıştırın. Visual C++ kitaplıklarının otomatik güncelleştirilmesini sağladıklarından, dağıtımlarınız için bu paketleri kullanmanızı öneririz. Bu paketlerin nasıl kullanılacağına ilişkin bir örnek için, bkz. [Izlenecek yol: Visual C++ yeniden dağıtılabilir paketi kullanarak Visual C++ uygulaması dağıtma](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

Her Visual C++ yeniden dağıtılabilir paket, makinede daha yeni bir sürümün varlığını denetler. Daha yeni bir sürüm bulunursa paket yüklenmez. Visual Studio 2015 ' den başlayarak yeniden dağıtılabilir paketler, Kurulumun başarısız olduğunu belirten bir hata mesajı görüntüler. Bir paket bayrağı kullanılarak çalışıyorsa **`/quiet`** , hata iletisi gösterilmez. Her iki durumda da, Microsoft yükleyicisi tarafından bir hata kaydedilir ve çağırana bir hata sonucu döndürülür. Visual Studio 2015 paketlerinde başlayarak, daha yeni bir sürümünün yüklü olup olmadığını öğrenmek için kayıt defterini denetleyerek bu hatadan kaçınabilirsiniz. Geçerli yüklü sürüm numarası `HKEY_LOCAL_MACHINE\SOFTWARE[\Wow6432Node]\Microsoft\VisualStudio\14.0\VC\Runtimes\{x86|x64|ARM}` anahtarda depolanır. Sürüm numarası, Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 için 14,0, en son yeniden dağıtılabilir, 2015 sürümü ile ikili uyumlu. Anahtar,, `ARM` `x86` veya `x64` platformun yüklü VCRedist sürümlerine bağlıdır. ( `Wow6432Node` Bir x64 platformunda yüklü x86 paketinin sürümünü görüntülemek Için regedit kullanıyorsanız alt anahtar altında onay yapmanız gerekir.) Sürüm numarası REG_SZ dize değerinde **`Version`** ve ayrıca,, **`Major`** **`Minor`** **`Bld`** ve **`Rbld`** `REG_DWORD` değerleri kümesinde depolanır. Yükleme zamanında bir hatadan kaçınmak için, şu anda yüklü olan sürüm daha yeni ise yeniden dağıtılabilir paket yüklemesini atlamanız gerekir.

## <a name="install-the-redistributable-merge-modules"></a>Yeniden dağıtılabilir birleştirme modüllerini yükler

Yeniden dağıtılabilir birleştirme modülleri, uygulamanızı dağıtmak için kullandığınız Windows Installer paketine (veya benzer yükleme paketine) dahil edilmelidir. Daha fazla bilgi için bkz. [birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md). Bir örnek için bkz. [Izlenecek yol: kurulum projesi kullanarak Visual C++ uygulaması dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

## <a name="install-individual-redistributable-files"></a>Tek başına yeniden dağıtılabilir dosyaları yükler

Yeniden dağıtılabilir DLL 'Leri *uygulamanın yerel klasörüne*doğrudan yüklemek de mümkündür. Yürütülebilir uygulama dosyanızı içeren klasör. Bakım nedenleriyle, bu yükleme konumunu kullanmanızı önermiyoruz.

## <a name="potential-run-time-errors"></a>Olası çalışma zamanı hataları

Windows, uygulamanız için gerekli olan yeniden dağıtılabilir kitaplık dll 'Lerden birini bulamazsa şuna benzer bir ileti görüntülenebilir: " *Library*. dll bulunamadığı için bu uygulama başlatılamadı. Uygulamayı yeniden yüklemek bu sorunu çözebilir. "

Bu tür bir hatayı gidermek için, uygulama yükleyicinizin doğru şekilde ayarlandığından emin olun. Yeniden dağıtılabilir kitaplıkların hedef sistemde doğru şekilde dağıtıldığını doğrulayın. Daha fazla bilgi için bkz. [bir Visual C++ uygulamasının bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md).

## <a name="related-articles"></a>İlgili makaleler:

[Birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md)\
Visual C++ çalışma zamanı kitaplıklarını klasöre paylaşılan DLL 'Ler olarak yüklemek için Visual C++ yeniden dağıtılabilir birleştirme modüllerinin nasıl kullanılacağını açıklar *`%windir%\system32\`* .

[Visual C++ ActiveX denetimlerini yeniden dağıtma](redistributing-visual-cpp-activex-controls.md)\
ActiveX Denetimlerini kullanan bir uygulamanın nasıl yeniden dağıtılması gerektiği açıklanmaktadır.

[MFC kitaplığını yeniden dağıtma](redistributing-the-mfc-library.md)\
MFC kullanan bir uygulamanın nasıl yeniden dağıtılacağı açıklanmaktadır.

[ATL uygulamasını yeniden dağıtma](redistributing-an-atl-application.md)\
ATL kullanan bir uygulamanın nasıl yeniden dağıtılacağını açıklar. Visual Studio 2012 ' den itibaren, ATL için yeniden dağıtılabilir kitaplık gerekli değildir.

[Dağıtım örnekleri](deployment-examples.md)\
Visual C++ uygulamalarının nasıl dağıtıldığını gösteren örneklere bağlantılar verir.

[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)\
Visual C++ dağıtım kavramlarını ve teknolojilerini tanıtır.

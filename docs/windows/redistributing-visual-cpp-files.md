---
title: Visual C++ Dosyalarını Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
ms.openlocfilehash: 2bf4297a6c61d16c68d6a9cb893aed78b9d7609d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787088"
---
# <a name="redistributing-visual-c-files"></a>Visual C++ Dosyalarını Yeniden Dağıtma

> [!NOTE]
> Bir Visual C++ çalışma zamanı dosyaları indirme için aradığınız çünkü burada misiniz? Git [Microsoft Web sitesi](http://www.microsoft.com/) girin **Visual C++ yeniden dağıtılabilir** arama kutusuna. İndirin ve bilgisayarınıza (64-bit Windows çalıştırıyorsanız Örneğin, x64) mimarisini ve Visual C++ sürümlerinden birini gereken (örneğin, 2015) yeniden dağıtılabilir paketi yükleyin.

Bir uygulamayı dağıtırken, onu desteklemek için gerekli tüm dosyaları da dağıtmalısınız. Bu dosyalardan herhangi biri Microsoft tarafından sağlanıyorsa, bunları yeniden dağıtma izniniz olup olmadığını kontrol edin. Visual Studio Lisans Koşulları'nı gözden geçirmek için IDE hakkında Microsoft Visual Studio iletişim kutusunda lisans koşulları bağlantısına bakın veya indirme [Microsoft Yazılımı Lisans koşulları](https://visualstudio.microsoft.com/license-terms/mlt687465/) dosya. Visual Studio'nun belirli sürümleri için Microsoft Yazılım Lisansı Koşullarındaki "Dağıtılabilir kod" bölümünde anılan "REDIST listesi" görüntülemek için bkz: [Microsoft Visual Studio 2017 ve Microsoft Visual Studio 2017 için dağıtılabilir kod SDK (içerir yardımcı programları ve BuildServer Dosyaları)](/visualstudio/productinfo/2017-redistribution-vs), veya Visual Studio 2015 için bkz. [Microsoft Visual Studio 2015 ve Microsoft Visual Studio 2015 SDK için dağıtılabilir kod](/visualstudio/productinfo/2015-redistribution-vs). Yeniden dağıtılabilir dosyalar hakkında daha fazla bilgi için bkz. [belirleme hangi DLL'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md) ve [Dağıtım örnekleri](deployment-examples.md).

Visual C++ yeniden dağıtılabilir dosyaları dağıtmak için Visual C++ yeniden dağıtılabilir paketleri kullanabilirsiniz (VCRedist\_x86.exe, VCRedist\_x64.exe veya VCRedist\_arm.exe) Visual Studio'ya dahildir. Visual Studio 2017'de, bu dosyaları Program dosyaları [(x86)] bulunabilir\\Microsoft Visual Studio\\2017\\_edition_\\VC\\Redist\\ MSVC\\_LIB sürüm_ klasörü, burada _edition_ Visual Studio sürümünün yüklü olduğundan ve _LIB sürüm_ sürümü dağıtılacağı kitaplıkları. Program dosyaları [(x 86)] \Microsoft Visual Studio Visual Studio 2015'te bu dosyalar, Visual Studio yükleme dizininde bulunabilir *sürüm*\VC\redist\\*yerel* \\. Program dosyaları [(x 86)] bulunabilir, Visual Studio 2017 yeniden dağıtılabilir birleştirme modülleri (.msm dosyaları) kullanmak için başka bir seçenektir\\Microsoft Visual Studio\\2017\\_edition_ \\ VC\\Redist\\MSVC\\_LIB sürüm_\\MergeModules\\ klasör. Visual Studio 2015'te bu modüller [(x 86)] Program Files \Common Files\Merge bulunabilir\\. Yeniden dağıtılabilir Visual C++ DLL'lerini doğrudan yüklemek mümkündür *uygulamanın yerel klasörüne*, uygulamanızın yürütülebilir uygulama dosyasını içeren klasör. Nedeni bakım için bu yükleme konumu kullanmanızı öneririz değil.

Visual C++ Yeniden Dağıtılabilir Paketleri tüm Visual C++ kitaplıklarını yükler ve kaydeder. Bu paketlerden birini kullanırsanız, uygulamanın yüklenmesi için bir önkoşul olarak hedef sistem üzerinde çalışacak şekilde ayarlamanız gerekir. Visual C++ kitaplıklarının otomatik güncelleştirilmesini sağladıklarından, dağıtımlarınız için bu paketleri kullanmanızı öneririz. Bu paketleri kullanma hakkında bir örnek için bkz [izlenecek yol: Visual C++ yeniden dağıtılabilir paketini kullanarak bir Visual C++ uygulamasını dağıtma](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

Her Visual C++ yeniden dağıtılabilir paketi makine üzerinde daha yeni bir sürüme bulunup bulunmadığını kontrol eder. Daha yeni bir sürümü bulunursa, paketi yüklü değil. Yeniden dağıtılabilir paketleri görünen Visual Studio 2015'ten başlayarak, Kurulum'un belirten bir hata iletisi başarısız oldu. Kullanarak bir paket çalıştırırsanız **/quiet** bayrağı, hata iletisi görüntülenir. Her iki durumda da Microsoft yükleyici tarafından bir hata günlüğe kaydedilir ve bir hata sonucu çağırana döndürülür. Visual Studio 2015 paketlerinde başlayarak, daha yeni bir sürümünün yüklü olup olmadığını öğrenmek için kayıt defterini kontrol ederek bu hatayı önleyebilirsiniz. Şu anda yüklü olan sürümü HKEY_LOCAL_MACHINE\Software [\Wow6432Node] \Microsoft\VisualStudio içinde depolanan\\_vs-version_\VC\Runtimes\\{x86 | x64 | ARM} anahtarı nerede _vs-version_ için Visual Studio sürüm numarasıdır (14.0 hem Visual Studio 2015 hem de Visual Studio 2017 için yeniden dağıtılabilir güncelleştirme 2017 ikili bir 2015 sürümü uyumlu olduğu için), ve anahtarın olduğu ARM x 86 veya x64 yüklü vcredist sürümleri platform için bağlı olarak. (Yüklü x86 sürümünü görüntülemek için RegEdit kullanmadığınız sürece Wow6432Node alt anahtarı altında kontrol gerekmez paket x x64 platformu.) Sürüm numarasını REG_SZ dize değerinde depolanan **sürüm** ve ayrıca kümesini **ana**, **küçük**, **Bld**ve **Rbld** REG_DWORD değerleri. Yükleme sırasında bir hatayı önlemek için şu anda yüklü olan sürümü daha yeniyse, yeniden dağıtılabilir paketinin yüklemesi atlamanız gerekir.

Visual C++ DLL içeren birleştirme modülü kullanıyorsanız, Windows Installer paketi (veya benzer yükleme paketi) uygulamayı dağıtmak için kullanmakta olduğunuz içermelidir. Daha fazla bilgi için [yeniden dağıtma tarafından kullanarak birleştirme modülleri](redistributing-components-by-using-merge-modules.md). Bir örnek için bkz [izlenecek yol: Bir Visual C++ Application By Using bir kurulum projesi dağıtma](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), yükleme paketi oluşturmak için InstallShield Limited Edition kullanmayı de gösterilmektedir.

## <a name="potential-run-time-errors"></a>Olası Çalışma Zamanı Hataları

Windows uygulamanız için gereken DLL'leri yeniden dağıtılabilir kitaplığı birini bulamazsa, şuna benzer bir ileti görüntülenebilir: "Bu uygulama başlatılamadı çünkü başaramadı *Kitaplığı*.dll bulunamadı. Uygulamanın yeniden yüklenmesi bu sorunu çözebilir."

Bu tür bir hatayı gidermek için uygulama Yükleyicinizle doğru bir şekilde derlendiğinden ve yeniden dağıtılabilir kitaplıklar hedef sistemde doğru bir şekilde dağıtıldığından emin olun. Daha fazla bilgi için [Visual C++ uygulaması bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md).

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Birleştirme modüllerini kullanarak yeniden dağıtma](redistributing-components-by-using-merge-modules.md)|Visual C++ yeniden dağıtılabilir birleştirme modülleri Visual C++ çalışma zamanı kitaplıklarını %windir%\system32\ klasörüne paylaşılan dll olarak yüklemek için nasıl kullanılacağını açıklar.|
|[Visual C++ ActiveX Denetimlerini Yeniden Dağıtma](redistributing-visual-cpp-activex-controls.md)|ActiveX Denetimlerini kullanan bir uygulamanın nasıl yeniden dağıtılması gerektiği açıklanmaktadır.|
|[MFC Kitaplığını Yeniden Dağıtma](redistributing-the-mfc-library.md)|MFC kullanan bir uygulamanın nasıl yeniden dağıtılacağı açıklanmaktadır.|
|[ATL uygulamasını yeniden dağıtma](redistributing-an-atl-application.md)|ATL kullanan bir uygulama dağıtılacağı açıklanmaktadır Visual Studio 2012'den itibaren yeniden dağıtılabilir kitaplık için ATL gereklidir.|
|[Dağıtım Örnekleri](deployment-examples.md)|Visual C++ uygulamalarının nasıl dağıtıldığını gösteren örneklere bağlantılar verir.|
|[Masaüstü uygulamalarını dağıtma](deploying-native-desktop-applications-visual-cpp.md)|Visual C++ dağıtım kavramlarını ve teknolojilerini tanıtır.|
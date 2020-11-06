---
title: Visual Studio’da C++
description: Windows, Linux, Android ve iOS için program geliştirmek üzere Visual Studio 'da Microsoft C/C++ derleyicisini, kod düzenleyicisini ve ilgili araçları nasıl kullanacağınızı öğrenin.
ms.date: 11/05/2020
ms.technology: cpp-ide
helpviewer_keywords:
- Visual C++, home page
ms.openlocfilehash: 32d8f45c1ae0ffeabcfd7b22988f125b138c1f4d
ms.sourcegitcommit: 12eb6a824dd7187a065d44fceca4c410f58e121e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2020
ms.locfileid: "94334162"
---
# <a name="c-in-visual-studio"></a>Visual Studio’da C++

:::moniker range="msvc-160"

> [!NOTE]
> Bu geliştirici belgeleri Visual Studio 2019 için geçerlidir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.
>
> Bir programı çalıştırabilmeniz için Microsoft Visual C++ 2019 yeniden dağıtılabilir paketi arıyorsanız, Microsoft Visual Studio sitenin [indirmeler](https://visualstudio.microsoft.com/downloads/) sayfasına gidin. **Tüm indirmeler** altında **diğer araçlar, çerçeveler ve yeniden dağıtılabilir** bölümünü genişletin. Hedef mimarinizi seçin ve ardından **İndir** düğmesini seçin.
>
> Eski yeniden dağıtılabilir için [eski indirmeler](https://visualstudio.microsoft.com/vs/older-downloads/) sayfasını açın. **Diğer araçlar, çerçeveler ve yeniden dağıtılabilir** bölümünü genişletin. İndirmek istediğiniz yeniden dağıtılabilir sürümü bulun, hedef mimarinizi seçin ve ardından **İndir** düğmesini seçin.

:::moniker-end

:::moniker range="msvc-150"

> [!NOTE]
> Bu geliştirici belgeleri Visual Studio 2017 için geçerlidir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.
>
> Bir programı çalıştırabilmeniz için Microsoft Visual C++ 2017 veya daha eski bir yeniden dağıtılabilir paketi arıyorsanız, Microsoft Visual Studio sitenin [daha eski indirmeler](https://visualstudio.microsoft.com/vs/older-downloads/) sayfasına gidin. **Diğer araçlar, çerçeveler ve yeniden dağıtılabilir** bölümünü genişletin. İndirmek istediğiniz yeniden dağıtılabilir sürümü bulun, hedef mimarinizi seçin ve ardından **İndir** düğmesini seçin.

:::moniker-end

:::moniker range="msvc-140"

> [!NOTE]
> Bu geliştirici belgeleri Visual Studio 2015 için geçerlidir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.
>
> Bir programı çalıştırabilmeniz için Microsoft Visual C++ 2015 veya daha eski bir yeniden dağıtılabilir paketi arıyorsanız, Microsoft Visual Studio sitenin [daha eski indirmeler](https://visualstudio.microsoft.com/vs/older-downloads/) sayfasına gidin. **Diğer araçlar, çerçeveler ve yeniden dağıtılabilir** bölümünü genişletin. İndirmek istediğiniz yeniden dağıtılabilir sürümü bulun, hedef mimarinizi seçin ve ardından **İndir** düğmesini seçin.

:::moniker-end

Microsoft Visual C++ (MSVC), Windows üzerinde Visual Studio 'nun bir parçası olarak kullanılabilen C++, C ve derleme dili geliştirme araçları ve kitaplıklarını ifade eder. Bu araçlar ve kitaplıklar, Evrensel Windows Platformu (UWP) uygulamaları, yerel Windows Masaüstü ve sunucu uygulamaları, Windows, Linux, Android ve .NET Framework iOS üzerinde çalışan platformlar arası kitaplıklar ve uygulamalar oluşturmanıza olanak sağlar. Basit konsol uygulamalarından herhangi bir şeyi, cihaz sürücülerinden ve işletim sistemi bileşenlerinden mobil cihazlara yönelik platformlar arası oyunlara ve en düşük IoT cihazlarından Azure bulutundaki çok sunuculu yüksek performanslı bilgi işlem cihazlarına yazmak için MSVC kullanabilirsiniz.

Visual Studio 2015, 2017 ve 2019 yan yana yüklenebilir. Visual Studio 2017 (v141) ve Visual Studio 2015 (v140) araç takımını kullanarak programları düzenlemek ve derlemek için Visual Studio 2019 (derleyici araç takımı v142) veya Visual Studio 2017 (v141) kullanabilirsiniz.

## <a name="whats-new-and-conformance-history"></a>Yenilikler ve uygunluk geçmişi

[Visual Studio 'da C++ yenilikleri](what-s-new-for-visual-cpp-in-visual-studio.md)\
Visual Studio 'daki yenilikleri öğrenin.

[Visual Studio 2003 ile 2015 arasındaki C++ yenilikleri](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
2003 ile 2015 arasında Visual Studio 'nun her sürümü için C++ ' daki yenilikleri öğrenin.

[Visual Studio 'da C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md)\
Visual Studio 'da C++ uyumluluk iyileştirmeleri hakkında bilgi edinin.

[Microsoft C++ dil uygunluğu tablosu](visual-cpp-language-conformance.md)\
MSVC C++ derleyicisinde özelliğe göre uygunluk durumu listesi.

[Microsoft C/C++ değişiklik geçmişi 2003-2015](../porting/visual-cpp-change-history-2003-2015.md)\
Önceki sürümlerdeki son değişiklikler hakkında bilgi edinin.

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Visual Studio 'Yu yükleyip önceki sürümlerden yükseltme

[Visual Studio 'da C++ desteğini yükler](../build/vscpp-step-0-installation.md)\
Visual Studio 'Yu indirin ve Microsoft C/C++ araç takımını yükleyin.

[Microsoft C++ taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)\
C++ standardına yönelik daha fazla derleyici uyumsuzluğuna ve Spectre azaltma gibi büyük ölçüde geliştirilmiş derleme sürelerinin ve güvenlik özelliklerinin avantajlarından yararlanmak için kod taşıma ve projeleri Visual Studio 2015 veya sonraki bir sürüme yükseltme Kılavuzu.

[Visual Studio sürümlerindeki C++ araçları ve özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)\
Farklı Visual Studio sürümleri hakkında bilgi edinin.

[Desteklenen platformlar](supported-platforms-visual-cpp.md)\
Microsoft C/C++ derleyicisinin desteklediği platformları öğrenin.

## <a name="learn-c"></a>C++ öğrenin

[C++ ' a geri hoş geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)\
C++ 11 ve üstünü temel alan modern C++ programlama teknikleri hakkında daha fazla bilgi edinmek için hızlı, güvenli kod yazmanızı ve C stili programlamayı birçok engel kullanmaktan kaçınmanızı sağlar.

[Standart C++](https://isocpp.org/)\
C++ hakkında bilgi edinin, Modern C++ hakkında genel bilgileri alın ve kitaplar, makaleler, konuşmalar ve olaylar için bağlantılara ulaşın

[Visual Studio 'Yu öğrenin ve ilk C++ projenizi yapın](../build/vscpp-step-1-create.md)\
Visual Studio 'da C++ yazma hakkında bilgi edinmeye başlayın.

[Visual Studio C++ örnekleri](visual-cpp-samples.md)\
Microsoft tarafından sağlanan C++ kod örnekleri hakkında bilgiler.

## <a name="c-development-tools"></a>C++ geliştirme araçları

[Visual Studio 'da C++ geliştirmeye genel bakış](overview-of-cpp-development.md)\
Visual Studio IDE 'yi kullanarak projeler oluşturma, kod düzenleme, kitaplıkları bağlama, derleme, hata ayıklama, birim testleri oluşturma, statik analiz, dağıtma ve daha fazlasını yapma.

[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)\
Visual Studio C++ projelerini, CMake projelerini ve MSVC derleyicisi ve bağlayıcı seçenekleriyle diğer proje türlerini oluşturma ve yapılandırma.

[C++ kodu yazma ve yeniden düzenleme](../ide/writing-and-refactoring-code-cpp.md)\
C++ düzenleyicisinde üretkenlik özelliklerini kullanarak kodu yeniden düzenleme, gezinme, anlama ve yazma.

[Yerel kodda hata ayıklama](/visualstudio/debugger/debugging-native-code)\
C++ projeleriyle Visual Studio hata ayıklayıcısını kullanın.

[C/C++ için kod analizi genel bakış](../code-quality/code-analysis-for-c-cpp-overview.md)\
Statik analiz yapmak için SAL ek açıklamalarını veya C++ Temel Yönergeleri denetleyicilerini kullanın.

[Visual Studio 'da C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp)\
C++, Google Test, Boost. test veya CTest için Microsoft birim testi çerçevesini kullanarak birim testleri oluşturun.

## <a name="write-applications-in-c"></a>C++ ' da uygulama yazma

[Evrensel Windows uygulamaları (C++)](../cppcx/universal-windows-apps-cpp.md)\
Kılavuzları ve referans içeriği Windows Geliştirici Merkezi'nde bulabilirsiniz. UWP uygulamaları geliştirme hakkında daha fazla bilgi için bkz. [Evrensel Windows platformu giriş](/windows/uwp/get-started/universal-application-platform-guide) ve [C++ kullanarak Ilk UWP uygulamanızı oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

[Masaüstü uygulamaları (C++)](../windows/desktop-applications-visual-cpp.md)\
Windows için geleneksel yerel C++ masaüstü uygulamaları oluşturmayı öğrenin.

[C++/CLı ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)\
C# veya Visual Basic gibi dillerde yazılmış yerel C++ ve .NET programları arasında birlikte çalışabilirliği etkinleştiren dll 'Leri oluşturmayı öğrenin.

[Linux Programlama](../linux/index.yml)\
Visual Studio IDE 'yi kullanarak, GCC ile derleme için uzak bir Linux makinesine kodlama ve dağıtma.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](../build/dlls-in-visual-cpp.md)\
Windows masaüstü DLL'leri oluşturmak için Win32, ATL ve MFC'nin nasıl kullanılacağını öğretir ve DLL dosyanızı nasıl derleyeceğiniz ve kaydedeceğiniz hakkında bilgiler sağlar.

[Paralel programlama](../parallel/parallel-programming-in-visual-cpp.md)\
Paralel Desenler Kitaplığı, C++ AMP, OpenMP ve Windows'ta çoklu iş parçacığı kullanımıyla ilişkili diğer özellikleri nasıl kullanacağınızı öğrenin.

[En iyi güvenlik uygulamaları](../security/security-best-practices-for-cpp.md)\
Uygulamaları kötü amaçlı kod ve yetkisiz kullanıma karşı nasıl koruyacağınızı öğrenin.

[Bulut ve Web programlama](../cloud/cloud-and-web-programming-in-visual-cpp.md)\
C++ ' da, Web ve buluta bağlanmak için çeşitli seçenekleriniz vardır.

[Veri erişimi](../data/data-access-in-cpp.md)\
ODBC ve OLE DB kullanarak veritabanlarına bağlanma.

[Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)\
Yerel ve uluslararası geliştirme için farklı metin ve dize biçimleri ve kodlamalar ile çalışma hakkında bilgi edinin.

## <a name="languages-reference"></a>Dil başvurusu

[C++ dil başvurusu](../cpp/cpp-language-reference.md)\
C++ programlama dilinin Microsoft uygulamasına başvuru kılavuzu.

[C/C++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)\
Paylaşılan C ve C++ dil ön işlemcisi için ortak bir başvuru.

[C dil başvurusu](../c-language/c-language-reference.md)\
C programlama dilinin Microsoft uygulamasına başvuru kılavuzu.

[Derleyici iç bilgileri ve derleme dili](../intrinsics/compiler-intrinsics-and-assembly-language.md)\
Her platformda Microsoft C/C++ derleyicileri tarafından desteklenen veya uygulanan derleyici iç derleyicisine kılavuzluk eder.

## <a name="c-libraries-in-visual-studio"></a>Visual Studio 'da C++ kitaplıkları

Aşağıdaki bölümlerde, Visual Studio 'Ya dahil edilen farklı C ve C++ kitaplıkları hakkında bilgi sağlanmaktadır.

[C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md)\
Güvenlik sorunlarına neden olduğu bilinen işlevlere alternatif olarak güvenliği artırılmış seçenekleri içerir.

[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)\
C++ Standart Kitaplığı.

[Etkin Şablon kitaplığı (ATL)](../atl/atl-com-desktop-components.md)\
COM bileşenleri ve uygulamaları için destek.

[Microsoft Foundation Class (MFC) kitaplıkları](../mfc/mfc-desktop-applications.md)\
Geleneksel veya Office stili kullanıcı arabirimleri olan masaüstü uygulamaları oluşturma desteği.

[Paralel Desenler kitaplığı (PPL)](../parallel/concrt/parallel-patterns-library-ppl.md)\
CPU üzerinde yürütülen zaman uyumsuz ve paralel algoritmalar.

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)\
GPU üzerinde yürütülen yoğun paralel algoritmalar.

[Windows Çalışma Zamanı şablon kitaplığı (WRL)](../cppcx/wrl/windows-runtime-cpp-template-library-wrl.md)\
Evrensel Windows Platformu (UWP) uygulamaları ve bileşenleri.

[C++/CLı ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)\
Ortak dil çalışma zamanı (CLR) için programlama.

## <a name="third-party-open-source-c-libraries"></a>Üçüncü taraf açık kaynak C++ kitaplıkları

Platformlar arası **vcpkg** komut satırı aracı, 900 ' den fazla C++ açık kaynak kitaplığı bulmayı ve yüklemesini büyük ölçüde basitleştirir. Bkz. [vcpkg: Windows Için C++ Paket Yöneticisi](../build/vcpkg.md).

## <a name="feedback-and-community"></a>Geri bildirim ve topluluk

[Microsoft Docs Q&A](/answers/topics/c%2B%2B.html)\
Microsoft Docs sorular ve yanıtlar için aranabilir forumları barındırır. `C++`C++ ile ilgili sorunlarda topluluk yardımı için gönderinize bir etiket ekleyin.

[Microsoft C/C++ araç takımı ile sorun bildirme](how-to-report-a-problem-with-the-visual-cpp-toolset.md)\
Microsoft C/C++ araç takımı (derleyici, bağlayıcı ve diğer araçlar) ve raporunuzu gönderme yöntemleri için etkili hata raporları oluşturmayı öğrenin.

Microsoft [C++ ekip blogu](https://devblogs.microsoft.com/cppblog/)\
Visual Studio 'da C++ araçlarının geliştiricilerinden yeni özellikler ve en son bilgiler hakkında daha fazla bilgi edinin.

[Visual Studio C++ geliştirici topluluğu](https://aka.ms/vsfeedback/browsecpp)\
Visual Studio 'da yardım alın, hataları dosyalayabilirsiniz ve C++ önerisi yapın.

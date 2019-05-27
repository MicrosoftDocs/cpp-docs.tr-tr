---
title: Visual Studio’da C++
description: Visual C++ için Microsoft C++ Derleyici, Kod Düzenleyicisi ve ilgili araçlar Visual Studio IDE'de addır. Programları Windows, Linux, Android ve iOS geliştirme için Visual C++ kullanın.
ms.date: 05/14/2019
ms.technology: cpp-ide
helpviewer_keywords:
- Visual C++, home page
author: mikeblome
ms.author: mblome
ms.openlocfilehash: e9327f74f46590f4d4a71e56340dcadf6527fabb
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174787"
---
# <a name="c-in-visual-studio"></a>Visual Studio’da C++

> [!NOTE]
> Bu Geliştirici belgeleri Visual Studio 2015 ve sonrası için geçerlidir. Sürüm Seçici, Visual Studio sürümünüze eşleştirmek için sayfanın sol üst içinde kullanın.
>
> Bir program çalıştırabilmek için Visual C++ yeniden dağıtılabilir paketi arıyorsanız, Git [Microsoft Download Center](http://www.microsoft.com/download/) girin **Visual C++** arama kutusuna.

Microsoft Visual Visual C++ ya da MSVC, genellikle kısalttık C++, C++, C ve derleme dili geliştirme araçları ve kitaplıkları kullanılabilir adıdır, Windows üzerinde Visual Studio'nun bir parçası olarak. Bu araçlar ve kitaplıklar, Evrensel Windows Platformu (UWP) uygulamaları, yerel Windows Masaüstü ve sunucu uygulamaları, platformlar arası kitaplıklar ve Windows, Linux, Android ve iOS, hem de yönetilen uygulamaları ve .NET kullanma kitaplıkları çalışan uygulamalar oluşturmanızı sağlar Çerçeve. Her şeyi basit bir konsol uygulamalardan en karmaşık ve karmaşık uygulamalar Windows Masaüstü için cihaz sürücüleri ve platformlar arası oyunlar mobil cihazları ve işletim sistemi bileşenleri için en küçük IOT cihazlarından yazmak için Visual C++ kullanabilirsiniz çok sunuculu yüksek performanslı Azure bulutta bilgi işlem.

Visual Studio 2015 ve 2017 2019 yüklü yan yana olabilir. Düzenle ve araç takımı (v140) Visual Studio 2015 ve Visual Studio 2017 (v141) kullanan programlar oluşturmak için Visual Studio 2019 (derleyici araç takımı v142) kullanabilirsiniz.

## <a name="whats-new-and-conformance-history"></a>Yenilikler ve uyumluluk geçmişi

[Visual Studio'da C++ için Yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
Visual Studio'daki yenilikleri öğrenin.

[Visual Studio 2003 ile 2015'teki c++ yenilikleri](../porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
C++'da yeni Visual Studio'nun her sürümü için 2003 ile 2015 arasındaki bulun.

[Visual Studio’deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md)<br/>
Visual Studio'da C++ uyumluluk geliştirmeleri hakkında bilgi edinin.

[Visual C++ dil uyumluluğu](visual-cpp-language-conformance.md)<br/>
MSVC C++ derleyicisinde özelliğiyle uygunluk durumu listesi.

[Visual C++ değişiklik geçmişi 2003 - 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
Önceki sürümler, bozucu değişiklikler hakkında bilgi edinin.

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Visual Studio'yu yükleyin ve önceki sürümlerinden yükseltme

[Visual Studio'ya C++ desteği yükleme](../build/vscpp-step-0-installation.md)<br/>
Visual Studio 2017 veya Visual Studio 2019 yükleyip, görsel C++ araç takımı.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)<br/>
Kod taşıma ve büyük derleyici uyumluluğu için yararlanmak için projeleri Visual Studio 2015 veya sonraki bir sürüme yükseltme için kılavuz C++ yanı sıra büyük ölçüde geliştirilmiş derleme sürelerini ve güvenlik özellikleri Spectre riskini azaltma gibi standart.

[Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)<br/>
Farklı Visual Studio sürümleri hakkında bilgi edinin.

[Desteklenen Platformlar](supported-platforms-visual-cpp.md)<br/>
Hangi platformların desteklendiğini öğrenin.

## <a name="learn-c"></a>Learn C++

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
Modern hakkında daha fazla bilgi C++ hızlı, güvenli kod yazma ve birçok C stili programlama düşebileceğiniz tuzakları önlemek etkinleştirdiğiniz C ++ 11 ve sonraki sürümlerde tabanlı programlama.

[Standart C++](http://isocpp.org/)<br/>
C++ hakkında bilgi edinin, Modern C++ hakkında genel bilgileri alın ve kitaplar, makaleler, konuşmalar ve olaylar için bağlantılara ulaşın

[Visual C++ öğrenin](../build/vscpp-step-1-create.md)<br/>
C++ öğrenmeye başlayın.

[Visual C++ Örnekleri](visual-cpp-samples.md)<br/>
Örnekler hakkında bilgi.

## <a name="c-development-tools"></a>C++ geliştirme araçları

[Visual Studio'da C++ geliştirme genel bakış](overview-of-cpp-development.md)<br/>
Visual Studio IDE kullanmak projeler oluşturun, kod düzenleme, kitaplıklarına bağlanması, derleme, hata ayıklama, birim testleri oluşturma, statik analiz yapmak için dağıtma ve daha.

[Projeler ve Derleme Sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
Nasıl oluşturun ve Visual Studio C++ projeleri, CMake projelerini ve diğer tür projelere MSVC derleyici ve bağlayıcı seçeneklerini yapılandırın.

[Yazma ve C++ kodu yeniden düzenleme](../ide/writing-and-refactoring-code-cpp.md)<br/>
Üretkenlik kullanmayı özellikleri C++ yeniden düzenleyin, Git, anlamak ve kod yazmak için düzenleyici.

[Yerel Kodda Hata Ayıklama](/visualstudio/debugger/debugging-native-code)<br/>
C++ projeleri Visual Studio hata ayıklayıcısını kullanın.

[C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)<br/>
Kullanım SAL ek açıklamaları veya statik analiz gerçekleştirmek için C++ temel yönergeleri denetleyicilerini.

[Visual Studio'da C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp)<br/>
C++, Google Test, Boost.Test veya CTest için Microsoft birim testi çerçevesini kullanarak birim testleri oluşturun.

## <a name="write-applications-in-c"></a>C++'da uygulamaları yazma

[Evrensel Windows uygulamaları](../windows/universal-windows-apps-cpp.md)<br/>
Kılavuzları ve referans içeriği Windows Geliştirici Merkezi'nde bulabilirsiniz. UWP uygulamaları geliştirme hakkında daha fazla bilgi için bkz: [Evrensel Windows platformu giriş](/windows/uwp/get-started/universal-application-platform-guide) ve [C++ kullanarak ilk UWP uygulamanızı oluşturmak](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

[Masaüstü uygulamaları (C++)](../windows/desktop-applications-visual-cpp.md)<br/>
Geleneksel yerel C++ Masaüstü uygulamaları için Windows oluşturmayı öğrenin.

[C++/CLI ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
C# veya Visual Basic gibi dillerde yazılan yerel C++ ve .NET programlar arasında birlikte çalışabilirliği sağlamak DLL'leri oluşturmayı öğrenin.

[Linux programlama](../linux/index.md)<br/>
Kodu Visual Studio IDE kullanın ve GCC ile derleme için bir uzak Linux makinesine dağıtın.

[Visual Studio'da C/C++ DLL'leri oluşturma](../build/dlls-in-visual-cpp.md)<br/>
Windows masaüstü DLL'leri oluşturmak için Win32, ATL ve MFC'nin nasıl kullanılacağını öğretir ve DLL dosyanızı nasıl derleyeceğiniz ve kaydedeceğiniz hakkında bilgiler sağlar.

[Paralel Programlama](../parallel/parallel-programming-in-visual-cpp.md)<br/>
Paralel Desenler Kitaplığı, C++ AMP, OpenMP ve Windows'ta çoklu iş parçacığı kullanımıyla ilişkili diğer özellikleri nasıl kullanacağınızı öğrenin.

[En iyi güvenlik uygulamaları](../security/security-best-practices-for-cpp.md)<br/>
Uygulamaları kötü amaçlı kod ve yetkisiz kullanıma karşı nasıl koruyacağınızı öğrenin.

[Bulut ve Web programlama](../cloud/cloud-and-web-programming-in-visual-cpp.md)<br/>
C++'da, web ve buluta bağlamak için birkaç seçeneğiniz vardır.

[Veri Erişimi](../data/data-access-in-cpp.md)<br/>
ODBC ve OLE DB kullanan veritabanlarına bağlanın.

[Metin ve Dizeler](../text/text-and-strings-in-visual-cpp.md)<br/>
Farklı metin ve dize biçimleri ve yerel ve uluslararası geliştirme için Kodlamalar ile çalışma hakkında bilgi edinin.

## <a name="languages-reference"></a>Dil Başvurusu

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)

[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)

[C Dil Başvurusu](../c-language/c-language-reference.md)

[Derleyici İç Bilgileri ve Derleme Dili](../intrinsics/compiler-intrinsics-and-assembly-language.md)

## <a name="c-libraries-in-visual-studio"></a>Visual Studio'da C++ kitaplıkları

Aşağıdaki bölümlerde, Visual Studio'ya dahil farklı C ve C++ kitaplıkları hakkında bilgi sağlar.

[C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)<br/>
Güvenlik sorunlarına neden olduğu bilinen işlevlere alternatif olarak güvenliği artırılmış seçenekleri içerir.

[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
C++ Standart Kitaplığı.

[Etkin Şablon Kitaplığı (ATL)](../atl/atl-com-desktop-components.md)<br/>
COM bileşenleri ve uygulamaları için destek.

[Microsoft Foundation Class (MFC) kitaplıkları](../mfc/mfc-desktop-applications.md)<br/>
Geleneksel veya Office stili kullanıcı arabirimleri olan masaüstü uygulamaları oluşturma desteği.

[Paralel Desen Kitaplığı (PPL)](../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
CPU üzerinde yürütülen zaman uyumsuz ve paralel algoritmalar.

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
GPU üzerinde yürütülen yoğun paralel algoritmalar.

[Windows çalışma zamanı Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)<br/>
Evrensel Windows Platformu (UWP) uygulamaları ve bileşenleri.

[C++/CLI ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
Ortak dil çalışma zamanı (CLR) için programlama.

## <a name="third-party-open-source-c-libraries"></a>Üçüncü taraf açık kaynak C++ kitaplıkları

Platformlar arası **vcpkg** komut satırı aracı bulma ve yükleme 900 C++ açık kaynak kitaplıkların büyük ölçüde basitleştirir. Bkz: [vcpkg: Windows için C++ Paket Yöneticisi](../build/vcpkg.md).

## <a name="feedback-and-community"></a>Geri bildirim ve topluluk

[Visual C++ Araç Takımıyla İlgili Bir Sorunu Bildirme](how-to-report-a-problem-with-the-visual-cpp-toolset.md)<br/>
Visual C++ araç takımı (Derleyici, bağlayıcı ve diğer araçları) ve raporunuzun göndermenin yolu karşı etkin hata raporlarını oluşturmayı öğrenin.

Microsoft [ C++ ekip blogu](https://devblogs.microsoft.com/cppblog/)<br/>
Yeni özellikler ve geliştiricilerinden en son bilgiler hakkında daha fazla bilgi C++ Visual Studio Araçları.

[Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/)<br/>
Visual Studio hakkında yardım almayı, hataları dosyalamayı ve öneride bulunmayı öğrenin.

## <a name="see-also"></a>Ayrıca bkz.

- [C Dil Başvurusu](../c-language/c-language-reference.md)
- [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
- [Derleyici İç Bilgileri ve Derleme Dili](../intrinsics/compiler-intrinsics-and-assembly-language.md)

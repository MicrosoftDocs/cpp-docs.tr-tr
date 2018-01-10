---
title: Visual Studio'da Visual C++ | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4eccca9e7afd26684d5845d853b4be98001cf58
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="visual-c-in-visual-studio"></a>Visual Studio'da Visual C++

Visual Studio 2017 programlama dili ve geliştirme araçları yerel Evrensel Windows uygulamaları, yerel Masaüstü ve sunucu uygulamaları, Android ve iOS aynı zamanda Windows çalıştıran ve .NET üzerinde çalışan uygulamalar yönetilen platformlar arası kitaplıkları geliştirmenize yardımcı Çerçeve.

**Bu belge için kim?**

Programları yazma C++ geliştiricileri için içeriktir.

- C++ yeniden dağıtılabilir paketi için aradığınız ve bir program çalıştırabilmeniz için çalışma zamanı bileşenleri Git [Microsoft Download Center](http://www.microsoft.com/en-us/download/) ve girin **Visual C++** arama kutusuna.

- C++ programlama kavramları giriş arıyorsanız, bu içerik sunan birçok Web sitesi birine gidin veya bir kopyasını almak [programlama--ilkeleri ve uygulama C++ (ikinci Edition) kullanarak](http://stroustrup.com/Programming/) C++, çalışan Bjarne stok tarafından Stroustrup. Visual C++ içerik C++ temel olarak bilindiğini zaten olduğunu varsayar.

- Visual Studio'dan ücretli veya ücretsiz bir sürümünü karşıdan yüklemeniz için Visual C++ derleyicisi arıyorsanız, [https://www.visualstudio.com/](https://www.visualstudio.com/).

## <a name="general-information-about-visual-c"></a>Visual C++ hakkında genel bilgiler

[Visual C++ için Yenilikler](what-s-new-for-visual-cpp-in-visual-studio.md)  
Visual C++ içindeki yenilikleri öğrenin.

[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md)  
Visual Studio 2017 C++ uygunluk geliştirmeler hakkında bilgi edinin.

[Visual C++ dili uyumluluğu](visual-cpp-language-conformance.md)  
Visual C++'ta özelliğiyle uygunluk durumu listesi.

[Visual C++ değişiklik geçmişi 2003 - 2015](porting/visual-cpp-change-history-2003-2015.md)  
Önceki sürümlerde önemli değişiklikler hakkında bilgi edinin.

[C++ için yeniden Hoş Geldiniz](cpp/welcome-back-to-cpp-modern-cpp.md)  
Güvenli kod modern C++ programlama C ++ 11 ve hızlı yazmanıza olanak tanıyan C ++ 14 göre teknikleri hakkında daha fazla bilgi ve C tarzı programlama Tuzaklar çoğunu kaçının.

[Visual C++ Araç Takımıyla İlgili Bir Sorunu Bildirme](how-to-report-a-problem-with-the-visual-cpp-toolset.md)  
 Visual C++ araç takımı (Derleyici, bağlayıcı ve başka araçlar) ve raporunuzu gönderme yolları karşı etkin hata raporlarını oluşturmayı öğrenin.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](porting/visual-cpp-porting-and-upgrading-guide.md)  
Kod bağlantı noktası oluşturma ve Windows 10 ve evrensel Windows platformu C++ kodu bağlantı noktası oluşturma dahil olmak üzere Visual Studio 2017'de Visual C++ projeleri yükseltme için kılavuz.

[Visual C++ ekip blogu](http://blogs.msdn.com/b/vcblog/)  
 Yeni özellikler ve geliştiricileri en son bilgileri hakkında daha fazla bilgi [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)].

[Visual Studio indirmeleri](http://go.microsoft.com/fwlink/p/?linkid=235233)  
Visual C++ indirin.

[Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)  
Farklı Visual Studio sürümleri hakkında bilgi edinin.

[Desteklenen Platformlar](supported-platforms-visual-cpp.md)  
Hangi platformların desteklendiğini öğrenin.

[Visual C++ Örnekleri](visual-cpp-samples.md)  
Örnekler hakkında bilgi.

[Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/)  
Visual Studio hakkında yardım almayı, hataları dosyalamayı ve öneride bulunmayı öğrenin.

## <a name="writing-applications-in-c"></a>C++ uygulamaları yazma

[Evrensel Windows uygulamaları](windows/universal-windows-apps-cpp.md)  
Kılavuzları ve referans içeriği Windows Geliştirici Merkezi'nde bulabilirsiniz. Windows mağazası uygulamaları geliştirme hakkında daha fazla bilgi için bkz: [Visual Studio kullanarak geliştirme Windows mağazası uygulamaları](http://go.microsoft.com/fwlink/p/?LinkId=248364) ve [C++ kullanarak Yol Haritası Windows mağazası uygulamaları için](http://go.microsoft.com/fwlink/p/?LinkId=244654).

[Masaüstü Uygulamaları (Visual C++)](windows/desktop-applications-visual-cpp.md)  
İleti döngüsü ve geri aramalar içeren masaüstü uygulamaları oluşturmayı öğrenin.

[Visual C++'ta DLL'ler](build/dlls-in-visual-cpp.md)  
Windows masaüstü DLL'leri oluşturmak için Win32, ATL ve MFC'nin nasıl kullanılacağını öğretir ve DLL dosyanızı nasıl derleyeceğiniz ve kaydedeceğiniz hakkında bilgiler sağlar.

[Paralel Programlama](parallel/parallel-programming-in-visual-cpp.md)  
Paralel Desenler Kitaplığı, C++ AMP, OpenMP ve Windows'ta çoklu iş parçacığı kullanımıyla ilişkili diğer özellikleri nasıl kullanacağınızı öğrenin.

[En iyi güvenlik uygulamaları](security/security-best-practices-for-cpp.md)  
Uygulamaları kötü amaçlı kod ve yetkisiz kullanıma karşı nasıl koruyacağınızı öğrenin.

[Bulut ve Web programlama](cloud/cloud-and-web-programming-in-visual-cpp.md)  
C++'da, web ve bulut bağlamak için birkaç seçeneğiniz vardır.

[Veri Erişimi](http://msdn.microsoft.com/Library/a9455752-39c4-4457-b14e-197772d3df0b)  
ODBC ve diğer veritabanı erişim teknolojilerini kullanarak veritabanlarına bağlanın.

[Metin ve Dizeler](text/text-and-strings-in-visual-cpp.md)  
Farklı bir metin ve dize biçimleri ve yerel ve uluslararası geliştirme Kodlamalar ile çalışma hakkında bilgi edinin.

## <a name="c-development-tools"></a>C++ geliştirme araçları

Projeleri oluşturma, kaynak kodu dosyaları ile çalışma, kitaplıklara, derleme, hata ayıklama, profil, dağıtmak ve daha fazlası hakkında bilgi almak için bkz: [IDE ve geliştirme araçları](ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="c-language-reference"></a>C++ Dil Başvurusu

C++ dili hakkında daha fazla bilgi için bkz: [C++ dil başvurusu](cpp/cpp-language-reference.md).

C++ önişlemci hakkında daha fazla bilgi için bkz: [C/C++ ön işlemci başvurusu](preprocessor/c-cpp-preprocessor-reference.md).

## <a name="c-libraries-in-visual-studio"></a>Visual Studio'da C++ kitaplıkları

Aşağıdaki bölümler, Visual C++ ile birlikte farklı C++ kitaplıkları hakkında bilgi sağlar.

[C Çalışma Zamanı Kitaplığı Başvurusu](c-runtime-library/c-run-time-library-reference.md)  
Güvenlik sorunlarına neden olduğu bilinen işlevlere alternatif olarak güvenliği artırılmış seçenekleri içerir.

[C++ Standart Kitaplığı](standard-library/cpp-standard-library-reference.md)  
C++ Standart Kitaplığı.

[Etkin Şablon Kitaplığı (ATL)](atl/atl-com-desktop-components.md)  
COM bileşenleri ve uygulamaları için destek.

[Microsoft Foundation Class (MFC) kitaplıkları](mfc/mfc-desktop-applications.md)  
Geleneksel veya Office stili kullanıcı arabirimleri olan masaüstü uygulamaları oluşturma desteği.

[Paralel Desen Kitaplığı (PPL)](parallel/concrt/parallel-patterns-library-ppl.md)  
CPU üzerinde yürütülen zaman uyumsuz ve paralel algoritmalar.

[C++ AMP (C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
GPU üzerinde yürütülen yoğun paralel algoritmalar.

[Windows çalışma zamanı Şablon kitaplığı (WRL)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
[!INCLUDE[win8_appname_long](build/includes/win8_appname_long_md.md)]uygulamaları ve bileşenleri.

[C++/CLI (Visual C++) ile .NET Programlama](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
Ortak dil çalışma zamanı (CLR) için programlama.

Ayrıca belgelerine bakın [STL/CLR](dotnet/stl-clr-library-reference.md) ve [C++ destek kitaplığı](dotnet/cpp-support-library.md).

## <a name="other-c-libraries"></a>Diğer C++ kitaplıkları

Bu bölümde, Visual Studio ile bulunmamaktadır ancak indirilebilen ve Visual C++ ile kullanılan kitaplıklarına bağlantılar içerir.

[Artırma](http://www.boost.org/)  
Popüler ve yaygın olarak kullanılan kitaplığı.

[C++ REST SDK](http://casablanca.codeplex.com).  
Web Hizmetleri ile HTTP üzerinden iletişim kuran bir Microsoft kitaplığı.

## <a name="more-resources"></a>Daha fazla kaynak

[Visual C++ kaynakları](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
Diğer Visual C++ kaynakları.

[Standart C++](http://isocpp.org/)  
C++ hakkında bilgi edinin, Modern C++ hakkında genel bilgileri alın ve kitaplar, makaleler, konuşmalar ve olaylar için bağlantılara ulaşın

[Visual C++ öğrenin](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
C++ öğrenmeye başlayın.

## <a name="see-also"></a>Ayrıca bkz.

[C Dil Başvurusu](c-language/c-language-reference.md)   
[C çalışma zamanı kitaplığı başvurusu](c-runtime-library/c-run-time-library-reference.md)   
[Derleyici İç Bilgileri ve Derleme Dili](intrinsics/compiler-intrinsics-and-assembly-language.md)

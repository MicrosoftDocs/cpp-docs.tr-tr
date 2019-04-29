---
title: Visual C++ taşıma ve yükseltme Kılavuzu
ms.date: 09/18/2018
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.openlocfilehash: 8798d8b3da5a91adfc6f77912d4f34bf62549f54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336926"
---
# <a name="visual-c-porting-and-upgrading-guide"></a>Visual C++ taşıma ve yükseltme Kılavuzu

Bu konuda, Visual C++ kod yükseltmek için bir kılavuz sağlar. Bu, yeni dil ve Visual Studio özelliklerinden yararlanarak yanı sıra Kodu derlemek ve Araçları'nın daha yeni bir yayın üzerinde doğru çalışması için alma içerir. Bu konu ayrıca daha modern platformlara geçirme eski uygulamaları hakkında bilgi içerir.

## <a name="reasons-to-upgrade-visual-c-code"></a>Visual C++ Kod yükseltme nedenleri

Aşağıdaki nedenlerden dolayı kodunuzun yükseltme dikkate almanız gerekir:

- Geliştirilmiş derleyici iyileştirmeleri nedeniyle daha hızlı kod.

- Daha hızlı, derleyici performans iyileştirmeleri nedeniyle oluşturur.

- Geliştirilmiş standartlara uyumluluk. Visual C++ artık birçok özelliklerinden en son C++ standartları uygular.

- Daha iyi güvenlik. Güvenlik özellikleri yaklaştırmalı gibi.

### <a name="porting-your-code"></a>Kodunuzu taşıma

Yükseltme sırasında uygulamanızın kod ve projeleri düşünün. Uygulamanızı Visual Studio ile yerleşik olarak bulunur? Bu durumda, ilgili projeleri belirleyin.  Özel derleme betikleri var mı? Visual Studio'nun derleme sistemi kullanmak yerine özel bir yapı komut dosyalarınız varsa, Visual Studio Proje dosyalarınızı güncelleştirmek ve derleme ayarlarını sağlayarak zaman kaydedilemiyor çünkü yükseltme yapılırken yapmak için daha fazla iş yüklemeniz gerekir.

Derleme sistemi ve proje dosyası biçimi Visual Studio sürümlerinde Visual Studio 2008 kadar vcbuild MSBuild'e ve sonraki sürümlerde 2010'dan Visual Studio sürümlerinde değiştirildi. 2010'dan önceki bir sürümünden yükseltme işleminiz olduğundan ve üst düzeyde özelleştirilmiş yapı sistemini yükseltmek daha fazla iş olabilir. Visual Studio 2010'dan yükseltme veya sonraki bir sürümü varsa, uygulamanız için yapı ve proje yükseltme daha kolay bu nedenle projelerinizi MSBuild, zaten kullanıyor.

Visual Studio'nun derleme sistemi kullanmıyorsanız, MSBuild kullanmayı düşünmelisiniz. MSBuild kullanmak için yükseltirseniz, gelecekteki yükseltmeler kolaylaştırmak amacıyla olabilir ve Visual Studio Online gibi hizmetleri kullanımı daha kolay olacaktır. MSBuild, Visual Studio'nun desteklediği tüm hedef platformlar destekler.

### <a name="porting-visual-studio-projects"></a>Visual Studio projelerini taşıma

Bir proje veya çözüm yükseltmeye başlamak için yalnızca yeni sürümünü Visual Studio içinde çözümü açın ve yükseltme başlatmak için istemleri takip edin.  Bir projeyi yükselttiğinizde, proje klasörünüzde UpgradeLog.htm olarak da kaydedilir bir yükseltme raporunu alın. Yükseltme raporunu yükseltme işlemi ve yapılan değişiklikler ya da otomatik olarak ele alınması değil sorunları hakkında bazı bilgiler sırasında karşılaşılan sorunları bir özeti gösterilir.

1. Proje Özellikleri

2. Dosyaları Ekle

3. Artık nedeniyle derleyici uyumluluğu imrovements düzgün bir şekilde derlenmesine veya değiştirir ve standart kod

4. Artık Visual Studio veya Windows özellikleri veya Visual Studio'nun varsayılan yüklemede bulunmayan veya üründen kaldırıldı üst bilgi dosyaları dayanan kod

5. Artık API değişiklikleri nedeniyle gibi derleme kodu API olarak yeniden adlandırıldı, işlev imzası değiştirildi veya İşlevler kullanım dışı

6. Uyarı hata olma gibi bir tanılama değişikliklerden dolayı artık derlenmemektedir kod

7. Bağlayıcı hataları nedeniyle özellikle/nodefaultlıb kullanılırken, değiştirilen kitaplıkları.

8. Çalışma zamanı hataları veya davranış değişiklikleri nedeniyle beklenmeyen sonuçlar

9. Hataları araçları tanıtılan hataları nedeniyle. Bir sorunla karşılaşırsanız, normal destek kanalları aracılığıyla ya da kullanarak Visual C++ ekibine rapor [Visual Studio geri bildirim Merkezi'ne](http://connect.microsoft.com/VisualStudio/Feedback).

Derleyici hataları nedeniyle yoksayılamaz değişikliklerin yanı sıra bazı değişiklikler gibi bir yükseltme işleminde isteğe bağlıdır:

1. Yeni uyarılar, kodunuzu oluşturan temizlemek istediğiniz anlamına gelebilir. Belirli tanılama bağlı olarak, bu taşınabilirlik, standartlara uyumluluk ve güvenlik kodunuzun artırabilir.

2. Yeni derleyici özelliklerini gibi yararlanmak isteyebilirsiniz [/Guard: cf (etkinleştirme akış denetimi koruyucu)](../build/reference/guard-enable-control-flow-guard.md) derleyici seçeneği, yetkisiz kod yürütme için denetimleri ekler.

3. Kodu basitleştirin, programlarınızın performansını yeni dil özelliklerini kullanmak için bazı kodlar güncelleştirmek istediğiniz veya modern kitaplıklarını kullanın ve modern standartları ve en iyi yöntemleri için kodu güncelleştirmeniz.

Yükseltme ve projenizi test sonra kodunuzu daha fazla iyileştirme düşünün veya gelecekteki yönü, kodunuzun planlayabilir ya da bile projenizi mimarisini yeniden gözden geçir isteyebilirsiniz. Bu durum, sürmekte olan geliştirme iş gönderilir mi? Diğer platformlar kodunuz için önemli olacak mı?  Bu durumda, hangi platformları?  C++ taşınabilirlik ve platformlar arası geliştirme düşünülerek tasarlanan standartlaştırılmış bir dil olan ve henüz çok sayıda Windows uygulamaları için kod Windows platformuna kesin bağlıdır. Daha fazla Windows platformuna bağlıdır parçaları kullanıma ayırmak için kodunuzu yeniden değiştirmenin istiyor musunuz?

Kullanıcı arabiriminizi hakkında neler diyeceksiniz? MFC kullanıyorsanız, kullanıcı arabirimini güncelleştirmek isteyebilirsiniz. Bir özellik paketi 2008'de kullanıma sunulan yeni MFC özelliklerinden herhangi birini kullanıyorsunuz? Uygulamanın tamamında yeniden yazma olmadan yeni bir görünümü ve deneyimini uygulamanıza verin istiyorsanız Şerit API'leri MFC'de veya MFC yeni özelliklerinden bazılarını kullanarak göz önünde bulundurabilirsiniz.

Bir XAML kullanıcı arabirimi, programınızın vermek istediğiniz, ancak bir UWP uygulaması oluşturmak istemiyorsanız, C# WPF ile yeniden düzenleme ve UI yerleşiminde DLL'lere standart C++ mantığınızı oluşturmak için kullanabilirsiniz. Bir birlikte çalışabilirlik katmanında oluşturun C++bağlanmak için /CLI C# yerel kodunuzla. Kullanarak bir UWP uygulaması oluşturmak için başka bir seçenektir [ C++/CX](https://msdn.microsoft.com/library/windows/apps/xaml/hh699871.aspx) veya [ C++/WinRT](https://github.com/microsoft/cppwinrt). Windows 10'da kullandığınız [masaüstü uygulaması dönüştürücü](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) herhangi bir kodu değiştirmek zorunda kalmadan bir UWP uygulaması olarak mevcut masaüstü uygulamanızı paketlemek için.

Alternatif olarak, artık belki de yeni gereksinimler ortaya veya Windows Masaüstü, Windows Phone veya Android cihazları gibi farklı platformları hedeflemek için gerekeceğini öngörüyorsanız. Kullanıcı arabirimi kodunuzu platformlar arası kullanıcı Arabirimi kitaplığı için bağlantı noktası. Bu UI çerçeveleri ile birden fazla cihazı hedefleyin ve geliştirme ortamı olarak Visual Studio ve Visual Studio hata ayıklayıcısını kullanmaya devam edebilirsiniz.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Visual C++'ın önceki sürümlerinde oluşturulmuş projeleri kullanmayı açıklar.|
|[Visual Studio'da C++ derleyicisi için yeni nedir](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)|IDE ve Araçlar, Visual Studio'nun geçerli sürümüne değişiklikleri|
|[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)|Visual Studio 2015 için Visual Studio standartlara uyumluluk geliştirmeleri|
|[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)|Visual C++ kitaplıkları ve kodunuzda değişiklikler gerektirebilir bir 2015 derleme araçları Visual Studio 2003'ten tüm değişikliklerin listesi.|
|[Visual C++ 2003 ile 2015 Arasındaki Farklar](visual-cpp-what-s-new-2003-through-2015.md)|Tüm "yenilikler" bilgileri için Visual Studio 2003 Visual Studio 2015 Visual C++.|
|[Üçüncü Taraf Kitaplıklarını Taşıma](porting-third-party-libraries.md)|Nasıl kullanılacağını **vcpkg** bağlantı noktası eski açık kaynak kitaplıkları daha yeni Visual C++ araç takımları ile derlenmiş sürümleri için komut satırı aracı.|
|[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](porting-and-upgrading-examples-and-case-studies.md)|Bu bölüm için biz unity'nin ve çeşitli örnekleri ve uygulamalar yükseltir ve sonuçları ve deneyimler ele alınan. Bu size okuma size bir fikir ne olduğunu taşıma ve yükseltme işlemi bulabilirsiniz. İşlemi boyunca size ipuçları ve püf noktaları yükseltme için tartışmanıza ve belirli hataları göster düzeltilmiştir.|
|[Evrensel Windows Platformu'na bağlantı noktası](porting-to-the-universal-windows-platform-cpp.md)|Windows 10 için kod bağlantı noktası oluşturma hakkında bilgi içerir.|
|[UNIX Kullanıcıları için Visual C++'a Giriş](introduction-to-visual-cpp-for-unix-users.md)|Visual C++'da yenidir ve onunla üretken isteyen UNIX kullanıcıları için bilgiler sağlar.|
|[UNIX'ten Win32'ye Taşıma](porting-from-unix-to-win32.md)|Windows UNIX uygulamalarını geçirme için seçenekleri açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++](../overview/visual-cpp-in-visual-studio.md)

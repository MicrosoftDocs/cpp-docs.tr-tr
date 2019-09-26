---
title: Görsel C++ taşıma ve Yükseltme Kılavuzu
ms.date: 09/18/2018
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: 55bfb9a1ad23a0e4a3efa7f0a9361523c6c9754d
ms.sourcegitcommit: 7750e4c291d56221c8893120c56a1fe6c9af60d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274683"
---
# <a name="visual-c-porting-and-upgrading-guide"></a>Görsel C++ taşıma ve Yükseltme Kılavuzu

Bu konu, görsel C++ kod yükseltmesi için bir kılavuz sağlar. Bu, araçların daha yeni bir sürümünde derleyip ve yeni dil ve Visual Studio özelliklerinden faydalanarak doğru bir şekilde kod almayı ve çalıştırmayı içerir. Bu konu başlığı altında, eski uygulamaların daha modern platformlara geçirilmesi hakkında bilgiler de yer alır.

## <a name="reasons-to-upgrade-visual-c-code"></a>Görsel C++ kodu yükseltme nedenleri

Aşağıdaki nedenlerden dolayı kodunuzu yükseltmeniz göz önünde bulundurmanız gerekir:

- Geliştirilmiş derleyici iyileştirmeleri nedeniyle daha hızlı kod.

- Derleyicinin kendisinde performans iyileştirmeleri nedeniyle daha hızlı derlemeler.

- İyileştirilmiş standartlar uygunluğu. Visual C++ artık en son C++ standartların birçok özelliğini uygular.

- Daha iyi güvenlik. Koruma denetimi gibi güvenlik özellikleri.

### <a name="porting-your-code"></a>Kodunuzun taşıma

Yükseltme sırasında öncelikle uygulamanızın kodunu ve projelerini düşünün. Uygulamanız Visual Studio ile oluşturulmuş mı? Bu durumda, dahil edilen projeleri tanımla.  Özel derleme betikleriniz var mı? Visual Studio 'nun derleme sistemini kullanmak yerine özel derleme betikleriniz varsa, yükseltme sırasında yapmanız gereken daha fazla iş olacaktır çünkü Visual Studio proje dosyalarınızı ve yapı ayarlarını güncelleştirerek zamandan tasarruf edebilirsiniz.

Visual Studio 'daki yapı sistemi ve proje dosyası biçimi, Visual Studio 2008 ' den Visual Studio 'nun 2010 ve sonraki sürümlerinde MSBuild 'e kadar olan Yükseltmeniz 2010 ' den önceki bir sürümyse ve yüksek düzeyde özelleştirilmiş bir derleme sistemine sahipseniz, yükseltmek için daha fazla iş yapmanız gerekebilir. Visual Studio 2010 veya sonraki bir sürümünü yükseltiyorsanız, projeleriniz zaten MSBuild kullanıyor, bu nedenle proje ve derlemeyi uygulamanız için yükseltmek daha kolay olmalıdır.

Visual Studio 'nun derleme sistemini kullanmıyorsanız, MSBuild 'i kullanmak için yükseltmeyi göz önünde bulundurmanız gerekir. MSBuild 'i kullanmak için yükseltirseniz, gelecekteki yükseltmelerde daha kolay bir zaman olabilir ve Visual Studio Online gibi hizmetleri kullanmak daha kolay olacaktır. MSBuild, Visual Studio 'Nun desteklediği tüm hedef platformları destekler.

### <a name="porting-visual-studio-projects"></a>Visual Studio projelerini taşıma

Bir projeyi veya çözümü yükseltmeye başlamak için, çözümü Visual Studio 'nun yeni sürümünde açmanız yeterlidir ve yönergeleri izleyerek yükseltmeyi başlatın.  Bir projeyi yükselttiğinizde, aynı zamanda proje klasörünüze UpgradeLog. htm olarak kaydedilen bir yükseltme raporu alırsınız. Yükseltme raporu, yükseltme işlemi sırasında karşılaşılan sorunlar ve yapılan değişikliklerle ilgili bazı bilgiler veya otomatik olarak giderilemeyen sorunlar hakkında bir Özet gösterir.

1. Proje Özellikleri

2. İçerme dosyaları

3. Derleyici uygunluğu veya standart değişiklikler nedeniyle artık düzgün derlenmeyecek kod

4. Visual Studio 'nun veya varsayılan bir Visual Studio yüklemesinde bulunmayan ya da üründen kaldırılmış olan üst bilgi dosyalarının kullanıldığı Visual Studio veya Windows özelliklerini kullanan kod

5. Yeniden adlandırılan API 'Ler, değiştirilen işlev imzaları veya kullanım dışı işlevler gibi API 'lerde yapılan değişiklikler nedeniyle artık derlenmediğini belirten kod

6. Bir hata haline gelme gibi Tanılamadaki değişiklikler nedeniyle artık derlenmediğini belirten kod

7. Özellikle/NODEFAULTLIB kullanıldığında değiştirilen kitaplıklar nedeniyle bağlayıcı hataları.

8. Davranış değişiklikleri nedeniyle çalışma zamanı hataları veya beklenmedik sonuçlar

9. Araçlarda sunulan hatalardan kaynaklanan hatalar. Bir sorunla karşılaşırsanız, normal destek kanallarınız aracılığıyla veya C++ [Visual Studio C++ geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfasını kullanarak bu sorunu görsel ekibe bildirin.

Derleyici hataları nedeniyle önleyebileceğiniz değişikliklere ek olarak, bazı değişiklikler bir yükseltme işleminde isteğe bağlıdır, örneğin:

1. Yeni uyarılar, kodunuzu temizlemek istediğiniz anlamına gelebilir. Bu, belirli tanılama 'ya bağlı olarak, kodunuzun taşınabilirlik, standartlar uyumluluğu ve güvenliğini iyileştirebilir.

2. Yetkisiz kod yürütme denetimleri ekleyen [/Guard: CF (Flow Control Guard 'ı etkinleştir)](../build/reference/guard-enable-control-flow-guard.md) derleyici seçeneği gibi daha yeni derleyici özelliklerinden yararlanmak isteyebilirsiniz.

3. Kodu basitleştiren yeni dil özelliklerini kullanmak, programlarınızın performansını geliştirmek veya modern standartları ve en iyi uygulamaları kullanmak için kodu güncelleştirmek üzere bazı kodları güncelleştirmek isteyebilirsiniz.

Projenizi yükselttikten ve test edildikten sonra, kodunuzun daha da iyileştirilmesi veya gelecekteki yönlerini planlamanız ya da projenizin mimarisini yeniden düşünmek isteyebilirsiniz. Devam eden geliştirme işi alacak mı? Kodunuzun diğer platformlarda çalışması için önemli olacak mı?  Öyleyse, hangi platformları?  C++, taşınabilirlik ve platformlar arası geliştirme ile tasarlanan standartlaştırılmış bir dildir ve henüz birçok Windows uygulaması için kod Windows platformuna bağlıdır. Windows platformuna daha fazla bağlanmış olan bölümleri ayırmak için kodunuzu yeniden düzenleme yapmak istiyor musunuz?

Kullanıcı arabiriminiz ne olacak? MFC kullanıyorsanız, Kullanıcı arabirimini güncelleştirmek isteyebilirsiniz. 2008 ' de bir özellik paketi olarak tanıtılan daha yeni MFC özelliklerinden birini kullanıyor musunuz? Uygulamanızı tüm uygulamayı yeniden yazmadan daha yeni bir görünüme sahip olmak istiyorsanız, MFC 'de şerit API 'Lerini kullanmayı veya MFC 'nin yeni özelliklerinden bazılarını kullanmayı düşünebilirsiniz.

Programınıza XAML kullanıcı arabirimi vermek ancak UWP uygulaması oluşturmak istemiyorsanız, Kullanıcı arabirimi katmanını oluşturmak ve standart C# C++ mantığınızı dll 'ler halınde yeniden oluşturmak için WPF ile birlikte kullanabilirsiniz. /CLI ' da C++yerel kodunuzla bağlantı C# kurmak için birlikte çalışabilirlik katmanı oluşturun. Diğer bir seçenek, [ C++/CX](../cppcx/visual-c-language-reference-c-cx.md) veya [ C++/wınrt](/windows/uwp/cpp-and-winrt-apis/)kullanarak UWP uygulaması oluşturmaktır. Windows 10 ' da, herhangi bir kodu değiştirmek zorunda kalmadan mevcut masaüstü uygulamanızı UWP uygulaması olarak paketlemek için [Masaüstü uygulaması dönüştürücüsünü](/windows/msix/desktop/desktop-to-uwp-run-desktop-app-converter) kullanabilirsiniz.

Alternatif olarak, artık yeni gereksinimleriniz olabilir veya Windows Phone veya Android cihazları gibi Windows Masaüstü dışındaki platformları hedefleme gereksinimini öngörülebilir bir şekilde görebilirsiniz. Kullanıcı arabirimi kodunuzun bir platformlar arası kullanıcı arabirimi kitaplığına bağlantı noktası oluşturabilirsiniz. Bu UI çerçeveleri sayesinde, birden çok cihazı hedefleyebilir ve Visual Studio ve Visual Studio hata ayıklayıcısını hala geliştirme ortamınız olarak kullanabilirsiniz.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Visual Studio 'nun önceki sürümlerinde oluşturulan projelerin nasıl kullanılacağını açıklar.|
|[Visual Studio 'daki C++ derleyicide yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)|IDE ve araçlarındaki değişiklikler, Visual Studio 'nun geçerli sürümüne göre|
|[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)|Visual Studio 2015 ile Visual Studio arasındaki standartlar uygunluk iyileştirmeleri|
|[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)|Visual Studio 2003 ile 2015 arasındaki tüm değişikliklerin C++ bir listesi ve kodunuzda değişiklik yapılmasını gerektirebilir.|
|[Visual C++ 2003 ile 2015 Arasındaki Farklar](visual-cpp-what-s-new-2003-through-2015.md)|Visual Studio 2015 aracılığıyla Visual Studio 2003 ' den görsel C++ için "yenilikler" bilgileri.|
|[Üçüncü Taraf Kitaplıklarını Taşıma](porting-third-party-libraries.md)|Daha yeni Visual C++ araçları kümeleriyle derlenen sürümlere daha eski açık kaynaklı kitaplıkların bağlantı noktası için **vcpkg** komut satırı aracını kullanma.|
|[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](porting-and-upgrading-examples-and-case-studies.md)|Bu bölümde, birkaç örnek ve uygulama ele alınmıştır ve bu deneyimleri ve sonuçları tartıştık. Bunları okumayı, taşıma ve yükseltme sürecinde nelerin bulunduğunu anlabileceğinizi fark edebilirsiniz. İşlemin tamamında, yükseltme için ipuçları ve püf noktaları tartışıyoruz ve belirli hataların düzeltilme şeklini gösteririz.|
|[Evrensel Windows Platformu taşıma](porting-to-the-universal-windows-platform-cpp.md)|Windows 10 ' a kod taşıma hakkında bilgi içerir|
|[UNIX Kullanıcıları için Visual C++'a Giriş](introduction-to-visual-cpp-for-unix-users.md)|Görsele C++ yenı olan UNIX kullanıcıları için bilgi sağlar ve bu verilerle üretken olmak ister.|
|[UNIX'ten Win32'ye Taşıma](porting-from-unix-to-win32.md)|UNIX uygulamalarının Windows 'a geçirilmesi için seçenekleri açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)

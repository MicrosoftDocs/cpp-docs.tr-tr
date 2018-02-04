---
title: "Visual C++ taşıma ve yükseltme Kılavuzu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5751899dc064da4b17e240411878187a80acbdc
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="visual-c-porting-and-upgrading-guide"></a>Visual C++ taşıma ve yükseltme Kılavuzu
Bu konu, Visual C++ kodu yükseltmek için bir kılavuz sağlar. Bu yeni dil ve Visual Studio özellikleri yararlanarak yanı sıra derlemek ve üzerinde daha yeni bir sürüm Araçları'nın düzgün çalışması için kodu alma içerir. Bu konu ayrıca daha modern platformlara geçirme eski uygulamalar hakkında bilgiler içerir.  
  
## <a name="reasons-to-upgrade-visual-c-code"></a>Visual C++ kodu yükseltme nedenleri  
 Aşağıdaki nedenlerden dolayı kodunuzun yükseltme dikkate almanız gerekir:  
  
-   Gelişmiş derleyici iyileştirmesi nedeniyle daha hızlı kodu.  
  
-   Daha hızlı, derleyici, performans iyileştirmeleri nedeniyle oluşturur.  
  
-   Geliştirilmiş standartlara uygunluk. Visual C++ şimdi son C++ standartları birçok özelliklerinden uygular.  
  
-   Daha iyi güvenlik. Kontrolü Görevlisi gibi güvenlik özellikleri.  
  
### <a name="porting-your-code"></a>Kodunuzu bağlantı noktası oluşturma  
 Yükseltme yaparken, uygulamanızın kodu ve projeleri düşünün. Uygulamanızı Visual Studio ile oluşturulur?  Bu durumda, söz konusu projeleri tanımlayın.  Özel derleme betiklerini var mı?  Visual Studio'nun yapı sistem kullanmak yerine özel bir yapı komut dosyaları varsa, Visual Studio Proje dosyalarınızı güncelleştirin ve yapı ayarları sağlayarak zaman kaydedilemiyor çünkü yükseltme yapılırken yapmak için daha fazla iş gerekir.  
  
 Derleme sistemi ve proje dosyası biçiminde Visual Studio sürümlerinde Visual Studio 2008 kadar vcbuild MSBuild için sonraki sürümlerde 2010'dan Visual Studio sürümlerinde değiştirildi. 2010 önce bir sürümünden yükseltme olduğundan ve bir yüksek oranda özelleştirilmiş yapı sistemi varsa, yükseltme için daha fazla iş yapmak gerekebilir.  Visual Studio 2010'dan yükseltme veya üzeri olması durumunda nedenle proje ve uygulamanız için derleme yükseltme daha kolay olmalıdır projelerinizi MSBuild, zaten kullanıyor.  
  
 Visual Studio'nun yapı sistem kullanmıyorsanız MSBuild kullanmak üzere yükseltmenin düşünmelisiniz. MSBuild kullanılacak yükseltirseniz, daha kolay bir saat içinde gelecekteki yükseltmeler olabilir ve Visual Studio Online gibi hizmetleri kullanmak daha kolay olacaktır. MSBuild Visual Studio destekleyen tüm hedef platformlar destekler.  
  
### <a name="porting-visual-studio-projects"></a>Visual Studio projelerini taşıma  
  Proje ya da çözüm yükseltmeye başlamak için yalnızca Visual Studio'nun yeni sürümünde çözümü açın ve onu yükseltmeye başlamak için istemleri izleyin.  Proje yükseltme yaparken de proje klasörünüzdeki UpgradeLog.htm olarak kaydedilmiş bir yükseltme raporu alın. Yükseltme raporunu yükseltme işlemi ve yapılan değişiklikler ya da otomatik olarak ele olmayan sorunlar hakkında bazı bilgileri sırasında karşılaşılan sorunları özetini gösterir.  
  
1.  Proje Özellikleri  
  
2.  Dosyaları dahil etme  
  
3.  Artık düzgün bir şekilde derleyici uyumluluğu imrovements nedeniyle derler veya standart değiştiren kodu  
  
4.  Artık kullanılabilir olmayan Visual Studio ya da Windows özellikleri veya Visual Studio varsayılan yüklemesinde bulunmayan veya Ürün kaldırıldı üstbilgi dosyaları güvenen kodu  
  
5.  Artık API'ler değişiklikleri nedeniyle gibi derler kod API'leri yeniden adlandırılmış, işlevi imzaları değiştirilen veya İşlevler kullanım dışı  
  
6.  Bir hata olma uyarı gibi tanılama değişiklikleri nedeniyle artık derler kodu  
  
7.  Bağlayıcı hataları nedeniyle özellikle /NODEFAULTLIB kullanıldığında, değiştirilen kitaplıkları.  
  
8.  Çalışma zamanı hataları veya davranış değişiklikleri nedeniyle beklenmeyen sonuçlar  
  
9. Araçları sunulan hatalar nedeniyle hatalar. Bir sorunla karşılaşırsanız, normal destek kanallarınıza veya kullanarak Visual C++ ekip için rapor [Visual Studio geri bildirim Merkezi](http://connect.microsoft.com/VisualStudio/Feedback).  
  
 Derleyici hataları nedeniyle yoksayılamaz değişiklikleri ek olarak, bazı değişiklikler gibi bir yükseltme işleminde isteğe bağlıdır:  
  
1.  Yeni uyarılar kodunuzu temizlemek istediğiniz anlamına gelir. Belirli tanılama bağlı olarak, bu taşınabilirlik, standartlara uygunluğu ve güvenlik kodunuzun iyileştirebilir.  
  
2.  Daha yeni derleyici özelliklerini gibi yararlanmak isteyebilirsiniz [/guard:cf (etkinleştirmek akış denetimi koruma)](../build/reference/guard-enable-control-flow-guard.md) yetkisiz kod yürütme denetimlerinin ekler derleyici seçeneği.  
  
3.  Kodu basitleştirmek, programlarınızı performansını yeni dil özellikleri kullanmak için bazı kod güncelleştirmek istediğiniz olabilir veya modern standartları ve en iyi uygulamalar ve modern kitaplıkları kullanmak için kodu güncelleştirin.  
  
 Yükseltme ve projenizin test sonra kodunuzu daha fazla iyileştirme göz önünde bulundurun veya kodunuzu gelecekteki yönü planlayabilir ya da hatta projenizi mimarisini alan isteyebilirsiniz. Devam eden geliştirme iş alacak? Diğer platformlar üzerinde çalışmak kodunuz için önemli olacak?  Öyleyse, hangi platformlar?  C++ taşınabilirlik ve platformlar arası geliştirme aklınızda tasarlanan standartlaştırılmış bir dil olan ve henüz çok sayıda Windows uygulamaları için kod Windows platformuna kesinlikle bağlıdır. Daha fazla Windows platformuna bağlıdır bu bölümleri çıkışı ayırmak için kodunuzu yeniden düzenlemeniz istiyor musunuz?  
  
 Kullanıcı Arabiriminizin nasıldır?  MFC kullanıyorsanız, kullanıcı arabirimini güncelleştirme isteyebilirsiniz.  Bir özellik paketi 2008'de sunulan yeni MFC özelliklerinden herhangi birini kullanıyor musunuz?  Yalnızca uygulamanız tüm uygulamayı yeniden yazma işlemi olmadan daha yeni bir görünüm ve kullanımında vermek istiyorsanız, API Şerit MFC'de veya MFC'nin yeni özelliklerden bazıları kullanarak düşünebilirsiniz.  
  
 Bir XAML kullanıcı arabirimi programınızı vermek istiyor, ancak bir UWP uygulaması oluşturmak istemiyorsanız, C# WPF ile düzenleme ve kullanıcı Arabirimi katmanı standart C++ mantığınızı DLL'lere oluşturmak için kullanabilirsiniz. Birlikte çalışabilirlik katman C + oluşturma +/ CLI C# ile yerel kodunuzu bağlanmak için. Kullanarak bir UWP uygulaması oluşturmak için başka bir seçenektir [C + +/ CX](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh699871.aspx) veya [C + +/ WinRT](https://github.com/microsoft/cppwinrt). Windows 10'da kullandığınız [masaüstü uygulaması dönüştürücü](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) herhangi bir kod değiştirmek zorunda kalmadan mevcut masaüstü uygulamanızı bir UWP uygulaması olarak paketlemek için.   
 Alternatif olarak, artık belki de yeni gereksinimler vardır veya Windows Phone ve Android cihazları gibi Windows Masaüstü dışındaki platformları hedeflemesi için gerekeceğini öngörüyorsanız. Kullanıcı arabirimi kodunuzu platformlar arası kullanıcı Arabirimi kitaplığı için bağlantı noktası. Bu UI çerçeveleri ile birden çok aygıt hedef de Visual Studio ve Visual Studio hata ayıklayıcısı geliştirme ortamınızı kullanabilirsiniz.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Visual C++ önceki sürümlerinde oluşturulan projelerin nasıl kullanılacağını açıklar.|  
|[Visual Studio 2017 RC, C++ derleyicisi'ne yönelik yeni nedir](../what-s-new-for-visual-cpp-in-visual-studio.md)|IDE içinde değiştirir ve Visual Studio 2017 Visual Studio 2015'ten araçları|  
|[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements-2017.md)|Visual Studio 2017 Visual Studio 2015'den standartlara uygunluk geliştirmeleri|  
|[Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md)|Visual C++ kitaplıkları ve kodunuzda değişiklikler gerektirebilir 2015 aracılığıyla derleme araçlarını Visual Studio 2003 tüm değişikliklerin bir listesi.|  
|[Visual C++ 2003 ile 2015 Arasındaki Farklar](visual-cpp-what-s-new-2003-through-2015.md)|Tüm "yenilikler" bilgileri Visual Studio 2015 ile Visual Studio 2003 Visual C++ için.|  
|[Üçüncü Taraf Kitaplıklarını Taşıma](porting-third-party-libraries.md)|Nasıl kullanılacağını **vcpkg** bağlantı noktası eski açık kaynak kitaplıkları ile daha yeni bir Visual C++ toolsets derlenmiş sürümleri için komut satırı aracı.|  
|[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](porting-and-upgrading-examples-and-case-studies.md)|Bu bölüm için şu bağlantı noktalı ve birkaç örneklerini ve uygulamaları yükseltir ve deneyimleri ve sonuçları açıklanır. Bu verir okuma, bir fikir ne olduğunu taşıma ve yükseltme işlemi söz konusu bulabilirsiniz. İşlemi boyunca size ipuçları ve püf noktaları yükseltme için ele almaktadır ve nasıl belirli hataları göster düzeltilmiştir.|  
|[Evrensel Windows Platformu'na bağlantı noktası oluşturma](porting-to-the-universal-windows-platform-cpp.md)|Windows 10 kod bağlantı noktası oluşturma hakkında bilgi içerir|  
|[UNIX Kullanıcıları için Visual C++'a Giriş](introduction-to-visual-cpp-for-unix-users.md)|Visual C++ için yenidir ve onunla üretken isteyen UNIX kullanıcıları için bilgi sağlar.|  
|[UNIX'ten Win32'ye Taşıma](porting-from-unix-to-win32.md)|Windows UNIX uygulamaları geçirme için seçenekleri açıklar.|  
|[C++/CLI Geçiş Öncüsü](../dotnet/cpp-cli-migration-primer.md)|Ayrıntılı olarak yükseltme, yeni sözdizimini kullanmak için için Yönetilen Uzantılar C++ söz dizimini gösterir. Daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++](../visual-cpp-in-visual-studio.md)

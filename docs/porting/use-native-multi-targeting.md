---
title: "Yerel çoklu sürüm desteği eski projeler derlemek için Visual Studio'da kullanın | Microsoft Docs"
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
helpviewer_keywords:
- C++ native multi-targeting
- upgrading Visual C++ applications, retargeting
ms.assetid: b115aabe-a9dc-4525-90d3-367d97ea20c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12fabf51f9a6d3db89ea544b5c3df1d59a6d5d02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="use-native-multi-targeting-in-visual-studio-to-build-old-projects"></a>Yerel çoklu sürüm desteği eski projeler derlemek için Visual Studio'da kullanın

Normalde, en son Visual Studio sürümünü yüklediğinizde projelerinizi güncelleştirmeniz önerilir. Projeler ve kod güncelleştirme uzaklığı yeni IDE, derleyici, kitaplıklar ve Araçlar avantajları tarafından genellikle daha maliyetidir. Ancak, bazı projeleri güncelleştirmek mümkün olmayabilir olduğunu bilirsiniz. Eski kitaplıkları veya bakım nedeniyle, yükseltemezsiniz platformları bağlı ikili dosyaları olabilir. Kodunuzu daha yeni bir derleyici taşınsa ihlal edeceğinden standart olmayan dil yapıları kullanabilirsiniz. Kodunuzu Visual C++, belirli bir sürümü için derlenmiş 3 taraf kitaplıkların bağlı. Veya Visual C++ özel bir eski sürümü hedeflemelidir başkaları için kitaplıkları üretebilir.

Neyse ki, bu hedef eski derleyici toolsets ve kitaplıkları projeler derlemek için Visual Studio 2017 ve Visual Studio 2015 kullanabilirsiniz. Visual Studio 2010, Visual Studio 2012, Visual Studio 2013 veya Visual Studio 2015 proje IDE'de yeni özelliklerden yararlanmak için yükseltme gerekmez:

 - Yeni C++ düzenleme yetenekleri ve düzenleyici Deneysel özellikleri
 - Yeni tanılama araçları penceresini ve hata listesi penceresini hata ayıklayıcı
 - Yenilenmiş kesme noktaları, özel durum pencere ve yeni PerfTips
 - Yeni kod gezinti ve arama araçları
 - Yeni C++ hızlı düzeltmeler ve üretkenlik güç araçları uzantıları.

Visual Studio 2008 projeleri hedefleyen, ancak bunlar kullanılamaz değişmez. Ayrıntılar için Visual Studio 2008 bölüm yönelik yönergelere bakın.

Yerel çoklu sürüm desteği ve projeleri gidiş en son Visual Studio sürümlerini destekler. Yerel çoklu sürüm desteği, Visual Studio'nun önceki sürümleri tarafından yüklenen toolsets kullanarak oluşturmak için en son IDE özelliğidir. Gidiş projeye hiçbir değişiklik yapmadan önceki bir IDE sürüm ile oluşturulan projeleri yüklemek için en son IDE özelliğidir. Varolan sürümünüzle Visual Studio yan yana en son sürümünü yüklerseniz, IDE yeni sürümünü derleyici ve mevcut sürümünden araçları ile projelerinizi oluşturmak için kullanabilirsiniz. Diğer ekibinizin üyeleri projeleri Visual Studio'nun daha eski sürümü kullanmaya devam edebilirsiniz.

Eski araç takımı kullandığınızda, en son IDE özelliklerin yanı sıra, en son gelişmeleri çoğunun C++ Derleyici, kitaplıklar ve derleme araçları yararlanabilirsiniz. Örneğin, yeni hata ayıklama yeni dil uygunluk iyileştirmeleri kullanabilir ve kod çözümleme özelliklerini veya son araç takımı daha hızlı derleme verimini elde olmayacaktır. Eski toolsets ile uyumlu olmayan bazı IDE özellikleri vardır. Örneğin, tür bilgilerini bellek profil oluşturucu ve yeniden düzenleme işlemi eksik olabilir **ham dize değişmez değerleri için dönüştürme** Visual Studio 2012 veya daha eski toolsets kullandığınızda, derleme olmaz C ++ 11 uyumlu kod oluşturur.

## <a name="how-to-use-native-multi-targeting-in-visual-studio"></a>Visual Studio'da yerel çoklu sürüm desteği kullanma

Eski sürüm ile Visual Studio yan yana yükledikten sonra Visual Studio yeni sürümde mevcut projenizi açın. Proje yüklendiğinde, Visual Studio son C++ derleyicisi ve kitaplıkları kullanacak şekilde yükseltme isteyip istemediğinizi sorar. Projeyi eski derleyici ve kitaplıkları tutmak istediğinden seçin **iptal** düğmesi.

Visual Studio, projenizin yükseltme hakkında kalıcıdır. Proje yüklenecek her zaman yükseltme iletişim kutusundan görmekten kaçınmak için aşağıdaki özellik projelerinizde tanımlayabilirsiniz veya .props veya .targets dosyaları bunlar içeri aktarın:

`<VCProjectUpgraderObjectName>NoUpgrade</VCProjectUpgraderObjectName>`

Projelerinizi yükseltmek istediğinizde, bu özellik kaldırmanız gerekir.

Yükseltme seçerseniz, Visual Studio çözüm ya da proje dosyalarınıza hiçbir değişiklik yapar. Projeyi derlerken oluşturulan ikili dosyalarını tamamen Visual Studio'nun daha eski sürümü ile oluşturulmuş olanları uyumludur. Visual Studio aynı C++ derleyicisi kullanır ve eski IDE'yi ile birlikte gelen aynı kitaplıkları bağlantılar olmasıdır. Ayrıca neden yükseltme iletişim kutusundan, daha eski Visual Studio sürüm seçerseniz yüklü tutmak için sizi uyarır olan **iptal**.

## <a name="instructions-for-visual-studio-2008"></a>Visual Studio 2008 için yönergeler  
  
Visual Studio 2008 VCBuild adlı C++ için kendi özel yapı sistem vardı. Visual Studio 2010'dan başlayarak, Visual C++ projeleri MSBuild kullanmak üzere değiştirilmiştir. Başka bir deyişle, Visual Studio 2008 projelerinizi Visual Studio'nın en son sürümünde oluşturmak için bir güncelleştirme adım aracılığıyla gitmeniz gerekir. Güncelleştirilmiş projeniz Visual Studio 2008 IDE kullanılarak oluşturulan ikili dosyalarını tamamen uyumlu ikili dosyaları yine oluşturur.

İlk olarak, Visual Studio'nun geçerli sürümü yanı sıra, Visual Studio 2010 Visual Studio 2008 ile aynı bilgisayarda yüklemeniz gerekir. Yalnızca Visual Studio 2010 Visual Studio 2008 projeleri hedefleyen için gereken MSBuild komut dosyalarını yükler. 

Ardından, Visual Studio'nun geçerli sürümü için Visual Studio 2008 çözüm ve projelerinizi güncelleştirmeniz gerekir. Proje ve çözüm dosyalarını yükseltmeden önce bir yedeğini oluşturun öneririz. Yükseltme işlemini başlatmak için çözümü Visual Studio'nun geçerli sürümünde açın. Yükseltme istemi aldığınızda, bilgileri gözden geçirin ve ardından **Tamam** yükseltme işlemini başlatmak için. Çözümde birden çok proje varsa, güncelleştirmeniz gerekir sihirbaz yeni .vcxproj proje dosyaları yan yana mevcut .vcproj dosyaları oluşturur. Ayrıca özgün .sln dosyasını bir kopyasına sahip olduğu sürece, yükseltme diğer mevcut Visual Studio 2008 projelerinizi üzerinde etkisi yoktur.

Yükseltme tamamlandığında günlük raporu hatalar veya uyarılar herhangi projeleriniz varsa dikkatle gözden geçirin. VCBuild dönüştürme MSBuild için sorunlara neden olabilir. Anlama ve raporda listelenen herhangi bir eylem öğesini uygulayan emin olun. Bu yükseltme günlüğüne rapor ve VCBuild MSBuild için dönüştürülürken ortaya çıkabilecek sorunlar hakkında daha fazla bilgi için bkz [C++ yerel çoklu sürüm desteği](https://blogs.msdn.microsoft.com/vcblog/2009/12/08/c-native-multi-targeting/) blog postası.

Proje yükseltme işlemi tamamlandıktan ve sorunları günlük dosyasında düzelttikten çözümünüzü gerçekten son araç takımı hedefler. Son adım olarak, Visual Studio 2008 araç takımı kullanmak için çözümdeki her proje için özelliklerini değiştirin. Visual Studio, geçerli sürümünü çözümdeki her proje için yüklenen çözümü ile projeyi açın **özellik sayfaları** iletişim kutusu: projeye sağ tıklayın **Çözüm Gezgini** ve ardından seçin **özellikleri**. İçinde **özellik sayfaları** iletişim kutusu, değişiklik **yapılandırma** aşağı açılan değer **tüm yapılandırmaları**. İçinde **yapılandırma özellikleri**seçin **genel**ve ardından değiştirmek **Platform araç takımı** için **Visual Studio 2008 (v90)**.

Bu değişiklikten sonra Visual Studio 2008 derleyici ve kitaplıkları, Visual Studio'nun geçerli sürümü çözümde derlerken proje ikili dosyaları oluşturmak için kullanılır.

## <a name="install-an-older-visual-studio-toolset"></a>Eski bir Visual Studio araç takımı yükleyin

Olamaz ya da yükseltmek istemediğiniz eski Visual C++ projesinde içerip projenizi eşleşen platform araç takımı sürümü olabilir. Bu durumda, araç takımı almak için ihtiyacınız olan sürümü Express sürümü ve ücretsiz Visual Studio Community yükleyebilirsiniz. Visual Studio 2008'de Visual Studio'dan her sürümü, derleyici, Araçlar ve geçerli Visual Studio'nun bu sürümü hedeflemek için gereken kitaplıklar yükleyebilirsiniz. Bul ve Visual Studio belirli bir sürümü indirmek için Microsoft Download Center arayın. Kurulum sırasında C++ yükleme seçenekleri seçtiğinizden emin olun. Kurulum tamamlandıktan sonra bu güncelleştirmeleri yüklemek için Visual Studio sürümünü çalıştırın. Ayrıca Windows Update değişiklikleri için gerekli olabilecek denetleyin. Bu güncelleştirme onay işlemi her bir güncelleştirme almak için birden çok kez yinelenmesi gerekir.

Gereksinim duyabileceğiniz Visual Studio indirmeleri bazıları şunlardır:

  - [Microsoft Visual Studio Community 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48146)  
  - [Windows Masaüstü Güncelleştirme 5 ile için Microsoft Visual Studio Express 2013](https://www.microsoft.com/en-us/download/details.aspx?id=48131)  
  - [Microsoft Visual Studio Express 2012 için Windows Masaüstü](https://www.microsoft.com/en-us/download/details.aspx?id=34673)  
  - [Visual Studio 2012 Güncelleştirme 5](https://www.microsoft.com/en-us/download/details.aspx?id=34673)  
  - [Microsoft Visual C++ 2010 Express (Web Yükleyicisi)](https://download.microsoft.com/download/1/D/9/1D9A6C0E-FC89-43EE-9658-B9F0E3A76983/vc_web.exe)  
  - [Microsoft Visual Studio 2010 Service Pack 1](https://www.microsoft.com/en-us/download/details.aspx?id=23691)  
  - [Microsoft Visual C++ 2008 Express SP1 (Web Yükleyicisi)](https://go.microsoft.com/?linkid=7729279)  

Bu ürünler yüklü olduğunda **Platform araç takımı** özelliği açılan **özellik sayfaları** iletişim kutusu kullanılabilir toolsets göstermek için otomatik olarak güncelleştirilir. En son sürümünü Visual Studio artık dönüştürme veya bunları yükseltme araç takımı bu eski sürümleri için projeleri oluşturmak üzere de kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements-2017.md)  

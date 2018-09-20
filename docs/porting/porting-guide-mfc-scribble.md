---
title: 'Taşıma Kılavuzu: MFC Scribble | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8230cf66fd3cc8cdce017c07f05f58b381ebd14
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400919"
---
# <a name="porting-guide-mfc-scribble"></a>Taşıma Kılavuzu: MFC Scribble

Bu konu Visual Studio 2017 için Visual Studio'nun eski sürümlerinde oluşturulmuş Visual C++ projeleri için yükseltme yordamını dağıtır çeşitli konular, davranıştır. Bu konular yükseltme işlemi çok basit bir proje ile başlayan ve biraz daha karmaşık ayarlara taşıma örnek tarafından tanıtmaktadır. Bu konu başlığında, yükseltme işlemi için belirli bir proje, MFC karalama üzerinden çalışıyoruz. C++ projeleri için yükseltme işlemi için temel bir giriş olarak uygun.  
  
Visual Studio'nun her sürümü Visual Studio'nun daha eski bir sürümden daha yeni bir tane taşıma kodu karmaşıklaştırabilir olası uyumsuzluklar tanıtır. Bazen gerekli kodunuzda derleyin ve kodunuzu güncelleştirmeniz gerekir ve bazen proje dosyaları için gerekli değişiklikleri olan değişikliklerdir. Visual Studio'nun önceki bir sürümüyle oluşturulmuş bir projeyi açtığınızda Visual Studio otomatik olarak bir proje veya çözüm en son sürüme güncelleştirilip güncelleştirilmeyeceğini ister. Bu araçlar, genellikle yalnızca proje dosyalarını yükseltme; Kaynak kodunuzu değiştirmeyin.  
  
## <a name="mfc-scribble"></a>MFC Scribble  
 
MFC karalama birçok farklı sürümlerinde Visual C++ dahil iyi bilinen bir örnektir. Bu MFC temel özelliklerinden bazılarını gösteren basit bir çizim uygulamasıdır. Çeşitli hem yönetilen hem de dahil olmak üzere, kullanılabilir ve yerel kod sürümleri vardır. Bu örnekte, karalama eski bir sürümü Visual Studio 2005'ten yerel kodda bulunan ve Visual Studio 2017'de açılır.  
  
Yükseltme işleminden önce Windows Masaüstü iş yükü yüklenmiş olduğundan emin olun. (Vs_installer.exe) Visual Studio Yükleyicisi'ni açın. Yükleyici açın yollarından biri açıklanmıştır seçmek için **dosya** > **yeni proje** ve kaydırma görene kadar yüklü şablonlar listesinden altına **açmak Visual Studio yükleyicisi**. Yükleyici açtıktan sonra tüm kullanılabilir iş yüklerinin görürsünüz. Varsa kutusunu **Windows Masaüstü** seçin ve tıklayın ardından iş yükü seçili **Değiştir** pencerenin alt kısmındaki düğmesi. 

Ardından, çözümün tamamını ve tüm içerikleri yedekleyin. 
 
Son olarak, yükseltme belirli yönteme karar vermek ihtiyacımız var. Daha karmaşık çözümleri ve uzun bir süredir yükseltilmemiş projeleri için Visual Studio'nun bir sürümü aynı anda yükseltme düşünmelisiniz. Bu şekilde, bir sorun, Visual Studio'nun hangi sürümünün sunulan aşağı daraltabilirsiniz. Basit bir proje için bu Visual Studio'nun en son sürümde açmaya çalışırken ve projeyi dönüştürmek sihirbazın değer olur. Bu işe yaramazsa, Visual Studio'nun uygun sürümleri erişiminiz varsa bir kerede bir sürümüne yükseltmeniz deneyebilirsiniz.  
  
Komut satırında devenv da çalıştırabileceğinizi unutmayın kullanarak `/Upgrade` projelerinizi Yükseltme Sihirbazı'nı kullanmak yerine seçeneği. Bkz: [Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe). Bu, çok sayıda projeleri için yükseltme işlemini otomatikleştirme yardımcı olabilir.  
  
### <a name="step-1-converting-the-project-file"></a>Adım 1. Proje dosyası dönüştürülüyor  

Visual Studio 2017'deki eski bir proje dosyasını açtığınızda, proje dosyası biz kabul en son sürüme dönüştürmek üzere Visual Studio sunar. Aşağıdaki iletişim kutusu görüntülendiğinde:  
  
![Proje ve çözüm değişikliklerini gözden](../porting/media/scribbleprojectupgrade.PNG "ScribbleProjectUpgrade")  
  
Itanium hedef kullanılamıyor ve dönüştürülmez bize bildiren bir hata oluştu.  
  
```Output  
Platform 'Itanium' is missing from this project. All the configurations and their file configuration settings specific to this platform will be ignored. If you want this platform converted, please make sure you have the corresponding platform installed under '%vctargetpath%\platforms\Itanium'.Continue to convert this project without this platform?  
```  
  
Önceki karalama projenin oluşturulduğu sırada, Itanium bir önemli hedef platformu da oldu. Artık Windows platformu, Itanium desteklediğinden, Itanium platformunu destekleyen olmadan devam etmek seçtik.  
  
Visual Studio, ardından tüm sorunların eski proje dosyasıyla birlikte listeleyen bir geçiş raporu görüntülenir.  
  
![Yükseltme raporu](../porting/media/scribblemigrationreport.PNG "ScribbleMigrationReport")  
  
Bu durumda, tüm uyarıları sorunları olan ve Visual Studio Proje dosyasında yapılan uygun değişiklikler. Proje endişe kadar derleme aracını MSBuild'e vcbuild değiştiğini büyük fark ise. Bu değişiklik, ilk Visual Studio 2010'da sunulmuştur. Diğer değişiklikler, proje dosyasının kendisini bazı yeniden öğelerin dizisi içerir. Sorunlarından hiçbiri, daha fazla dikkat bu basit proje için gereklidir.  
  
### <a name="step-2-getting-it-to-build"></a>Adım 2. Derleme için alma  

Proje sistemi kullanarak hangi derleme sürümünün biliyoruz şekilde yapılandırmadan önce biz platform araç takımını denetleyin. Proje Özellikleri iletişim kutusunda, altında **yapılandırma özellikleri**, **genel** kategori göz **Platform araç takımını** özelliği. Bu sürümü Visual Studio ve bu durumda v141 araçları Visual Studio 2017 sürümü için platform Aracı sürüm numarasını içerir. Visual C++ 2010 ile derlenmiş bir proje dönüştürdüğünüzde, 2012, 2013 veya 2015 araç takımı otomatik olarak Visual Studio 2017 araç takımını güncelleştirilmez.   
  
Unicode'a geçiş yapmak için projenin özelliklerini açmak **yapılandırma özellikleri**, seçin **genel** bölümünde ve bulun **karakter kümesi** özelliği. Bu değişiklik **çok baytlı karakter kümesi kullanan** için **Unicode karakter kümesini Kullandırır**. Bu değişikliğin etkilerini o artık _UNICODE ve UNICODE makroları tanımlanır ve _MBCS değil, Özellikler iletişim kutusunda altında doğrulayabilirsiniz **C/C++** kategori **komut satırı** özelliği.  
  
```Output  
/GS /analyze- /W4 /Zc:wchar_t /Zi /Gm- /Od /Fd".\Debug\vc141.pdb" /Zc:inline /fp:precise /D "_AFXDLL" /D "WIN32" /D "_DEBUG" /D "_WINDOWS" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX /Zc:forScope /Gd /Oy- /MDd /Fa".\Debug\" /EHsc /nologo /Fo".\Debug\" /Fp".\Debug\Scribble.pch" /diagnostics:classic 
```  
  
Karalama proje Unicode karakterleriyle derlemek için ayarlanmış durumda olsa da, hiçbir şey gerçekten değiştirilmesi gereken şekilde zaten TCHAR ile char yerine yazılmış. Proje başarıyla Unicode karakter kümesi ile oluşturulur.  
  
Artık çözümü oluşturun. Çıktı penceresinde, bize bu _WINNT32_WINNT tanımlanmamış derleyiciye:  
  
```Output  
_WIN32_WINNT not defined. Defaulting to _WIN32_WINNT_MAXVER (see WinSDKVer.h)  
```  
  
Bu uyarı, bir hata ve Visual C++ proje yükseltme sırasında yaygın olarak görülür. Uygulamamızı üzerinde çalışacak Windows en düşük sürümünü tanımlayan makro budur. Şu uyarıyı yoksay, biz geçerli Windows sürümü anlamına _WIN32_WINNT_MAXVER varsayılan değeri kabul edin. Olası değerler tablo için bkz: [Windows üst bilgileri kullanma](/windows/desktop/WinProg/using-the-windows-headers). Örneğin, size tüm sürümlerde Vista ve sonraki sürümlerde çalıştırmak için ayarlayabilirsiniz.  
  
```cpp
#define _WIN32_WINNT _WIN32_WINNT_VISTA  
```  
  
Kodu Windows API ile bu makroyu belirttiğiniz Windows sürümünde kullanılamayan bölümleri kullanıyorsa, bir derleyici hatası görmeniz gerekir. Karalama kod söz konusu olduğunda, hata yoktur.  
  
### <a name="step-3-testing-and-debugging"></a>Adım 3. Test ve hata ayıklama  

Hiçbir test paketi için uygulamayı kullanmaya yeni özellikleri kullanıcı Arabirimi aracılığıyla el ile test yok. Hiçbir sorun gözlemlenmedi.  
  
### <a name="step-4-improve-the-code"></a>4. adımı. Kodu geliştirecek  

Visual Studio 2017'ye geçiş yaptıktan sonra yeni C++ özellikleri yararlanmak için bazı değişiklikler yapmak isteyebilirsiniz. Geçerli C++ derleyicisi C++ Standart sonra önceki sürümleri için çok daha fazla uyumlu bir göz önünde varsa, kodunuzu daha güvenli ve daha taşınabilir hale getirmek için diğer derleyiciler için bazı kod değişiklikleri ve işletim sistemleri, bazı düşünmelisiniz sürümüdür geliştirmeleri.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 
Karalama küçük ve basit Windows masaüstü uygulaması olduğundan ve dönüştürmek sabit değildi. Birçok küçük, basit uygulamaları kolayca yeni sürüme dönüştürün.  Daha fazla kod satır sayısını, modern mühendislik standartları kadar olmayabilir eski eski kod ile daha karmaşık uygulamalar için birden çok projeye ve kitaplıkları, özel derleme adımları veya karmaşık betikleştirilmiş otomatik derlemeler için yükseltmek için daha uzun sürer. Devam [sonraki örnekte](../porting/porting-guide-com-spy.md), COM Spy adlı ATL/COM uygulama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Sonraki örnek: COM Spy](../porting/porting-guide-com-spy.md)
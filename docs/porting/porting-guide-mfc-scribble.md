---
title: "Taşıma Kılavuzu: MFC karalama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7288b343563056f6e1daa4f0cb61b43fb263792f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="porting-guide-mfc-scribble"></a>Taşıma Kılavuzu: MFC Scribble
Visual Studio için Visual Studio 2017 eski sürümlerinde oluşturulan Visual C++ projeleri için yükseltme yordamını dağıtır çeşitli konular ilk konudur. Bu konularda yükseltme işlemi oldukça basit bir proje ile başlayan ve biraz daha karmaşık olanları taşıma örneği tarafından tanıtır. Bu konuda, belirli bir projenin, MFC karalama yükseltme sürecinde size çalışır. C++ projeleri için uygun yükseltme işlemi için temel bir giriş olarak.  
  
 Visual Studio her sürümü Visual Studio'nun daha eski bir sürümü taşıma koddan daha yeni karmaşık hale getirebilir olası uyumsuzlukları tanıtır. Bazen derlenir ve kodunuzu güncelleştirin ve gerekli değişiklikleri bazen proje dosyalarına olan kodunuzda gerekli değişiklikleri olduğundan. Visual Studio'nun önceki bir sürümüyle oluşturulmuş bir projeyi açtığınızda Visual Studio otomatik olarak proje ya da çözüm en son sürüme güncelleştirilip güncelleştirilmeyeceğini ister. Bu araçlar genellikle yalnızca proje dosyalarını yükseltme; kaynak kodunuz değişiklik yapmayın.  
  
## <a name="mfc-scribble"></a>MFC Scribble  
 MFC karalama, birçok farklı Visual C++ sürümlerinde bulunan iyi bilinen bir örnektir. MFC temel özelliklerden bazıları gösterilir basit bir çizim uygulaması değil. Çeşitli, yönetilen her ikisi de dahil olmak üzere, kullanılabilir ve yerel kod sürümlerini vardır. Bu örnek için Visual Studio 2005'ten yerel kodda karalama eski bir sürümü bulundu ve Visual Studio 2017 açılır.  
  
 Yükseltme işleminden önce yüklü Windows Masaüstü iş yükü sahip olduğunuzdan emin olun. Visual Studio Yükleyicisi (vs_installer.exe) açın. Yükleyici açmak için bir yol olduğundan dosya seçmek üzere | Yeni proje ve yüklenmiş şablonlar, kadar listenin aşağısına kaydırın "Açık Visual Studio yükleyicisi" konusuna bakın. Yükleyici açtıktan sonra tüm kullanılabilir iş yüklerinin görürsünüz. Windows Masaüstü iş yükü için kutusu seçili değilse, onu seçin ve pencerenin altındaki Değiştir düğmesini tıklatın. 


 Ardından, tüm çözümü ve tüm içeriğini yedekleyin. 
 
 Son olarak, biz yükseltme belirli yöntemine karar verin gerekli. Daha karmaşık çözümler ve uzun bir süredir yükseltilmemiş projeler için aynı anda bir Visual Studio sürümüne yükseltme düşünmelisiniz. Bu şekilde, bir sorun Visual Studio sürümünü sunulan aşağı daraltabilirsiniz. Basit bir proje için bu en son Visual Studio sürümünde açılmaya çalışılırken ve projeyi dönüştürmek için Sihirbazı'nı izin vererek değer olur. Bu işe yaramazsa, Visual Studio'nun uygun sürümleri erişiminiz varsa bir kerede tek bir sürümünden yükseltme deneyebilirsiniz.  
  
 Komut satırında devenv da çalıştırabileceğinizi unutmayın kullanarak `/Upgrade` projelerinizi Yükseltme Sihirbazı'nı kullanarak yerine seçeneği. Bkz: [Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe). Bu, çok sayıda projeleri için yükseltme işlemini otomatik hale getirmede yardımcı olabilir.  
  
### <a name="step-1-converting-the-project-file"></a>Adım 1. Proje dosyası dönüştürme  
 Visual Studio 2017 ' eski bir proje dosyası açtığınızda Visual Studio Proje dosyası biz kabul en son sürüme dönüştürmek üzere sunar. Aşağıdaki iletişim kutusu görüntülendiğinde:  
  
 ![Proje ve çözüm değişiklikleri gözden](../porting/media/scribbleprojectupgrade.PNG "ScribbleProjectUpgrade")  
  
 Itanium hedef kullanılabilir değil ve dönüştürülen olmaz bize bildiren bir hata oluştu.  
  
```Output  
Platform 'Itanium' is missing from this project. All the configurations and their file configuration settings specific to this platform will be ignored. If you want this platform converted, please make sure you have the corresponding platform installed under '%vctargetpath%\platforms\Itanium'.Continue to convert this project without this platform?  
```  
  
 Önceki karalama projenin oluşturulduğu zaman, Itanium önemli hedef platformu oluştu. Windows platformu artık Itanium, destekler, böylece Itanium platformu destekleme olmadan devam etmek seçtik.  
  
 Visual Studio ardından sorunların tümünü eski proje dosyasıyla birlikte listeleyen bir geçiş rapor görüntülenir.  
  
 ![Yükseltme raporu](../porting/media/scribblemigrationreport.PNG "ScribbleMigrationReport")  
  
 Bu durumda, tüm uyarıları sorunları olan ve Visual Studio Proje dosyasında yapılan uygun değişiklikler. Proje kaygı oldukça büyük oluşturma aracını msbuild için vcbuild değiştirilen farktır. Bu değişiklik ilk Visual Studio 2010'da sunulmuştur. Diğer değişiklikler, öğeleri dizi bazı yeniden düzenleme yapılmasını proje dosyasının kendisini içerir. Sorunlardan hiçbiri dikkat daha basit bu proje için gereklidir.  
  
### <a name="step-2-getting-it-to-build"></a>Adım 2. Derleme için alma  
 Proje sistemini kullanarak hangi derleyici sürümü biliyoruz şekilde yapılandırmadan önce biz platform araç takımı denetleyin. Proje Özellikleri iletişim kutusunda, altında **yapılandırma özellikleri**, **genel** kategorisi, göz **Platform araç takımı** özelliği. Visual Studio ve bu durumda v141 araçları Visual Studio 2017 sürümü için ise platform Aracı sürüm numarasını sürümünü içerir. İlk olarak Visual C++ 2010 ile derlenen bir proje dönüştürürken 2012, 2013 veya 2015, araç takımı otomatik olarak Visual Studio 2017 toolset güncelleştirilmez.   
  
  Unicode geçiş yapmak için projenin özelliklerini açmak **yapılandırma özellikleri**, seçin **genel** bölümünde ve bulun **karakter kümesi** özelliği. Bu değişiklik **çok baytlı karakter kümesi kullanan** için **Unicode karakter kümesi kullanan**. Bu değişikliğin etkisini bu şimdi _UNICODE ve UNICODE makroları tanımlanır ve _MBCS değil, hangi Özellikler iletişim kutusunda altında doğrulayabilirsiniz **C/C++** kategorisindeki **komut satırı** özelliği.  
  
```Output  
/GS /analyze- /W4 /Zc:wchar_t /Zi /Gm- /Od /Fd".\Debug\vc141.pdb" /Zc:inline /fp:precise /D "_AFXDLL" /D "WIN32" /D "_DEBUG" /D "_WINDOWS" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX /Zc:forScope /Gd /Oy- /MDd /Fa".\Debug\" /EHsc /nologo /Fo".\Debug\" /Fp".\Debug\Scribble.pch" /diagnostics:classic 
```  
  
 Karalama proje Unicode karakterler derlemek için ayarlanmış edilmedi ancak hiçbir şey gerçekte değiştirilmesi gereken şekilde zaten ile TCHAR char yerine yazıldıysa. Proje başarıyla Unicode karakter kümesi ile oluşturulur.  
  
 Şimdi çözümü oluşturun. Bu _WINNT32_WINNT tanımlı değil çıktı penceresinde derleyici bize bildirir:  
  
```Output  
_WIN32_WINNT not defined. Defaulting to _WIN32_WINNT_MAXVER (see WinSDKVer.h)  
```  
  
 Bu uyarı, bir hata ve Visual C++ projesi yükseltirken çok yaygındır. Hangi en düşük Windows sürümü ile uygulamamız çalışacak tanımlar makrosu budur. Şu uyarıyı yok sayarsanız biz varsayılan değeri, geçerli Windows sürümü anlamına gelir _WIN32_WINNT_MAXVER kabul edin. Olası değerler tablo için bkz: [anlamıyla](https://msdn.microsoft.com/en-us/library/aa383745.aspx). Örneğin, size herhangi bir sürümünde veya sonraki sürümleri Vista'dan çalıştıracak şekilde ayarlayabilirsiniz.  
  
```  
#define _WIN32_WINNT _WIN32_WINNT_VISTA  
```  
  
 Kod Windows API ile bu makrosu belirttiğiniz Windows sürümünde kullanılamaz bölümlerini kullanıyorsa, derleyici hatası görmeniz gerekir. Karalama kodu söz konusu olduğunda, herhangi bir hata yoktur.  
  
### <a name="step-3-testing-and-debugging"></a>Adım 3. Test ve hata ayıklama  
 Hiçbir test paketi biz yalnızca uygulaması başlatıldı şekilde özelliklerini kullanıcı Arabirimi aracılığıyla el ile test yoktur. Herhangi bir sorun gözlenen.  
  
### <a name="step-4-improve-the-code"></a>4. adım. Kod geliştirmek  
 Visual Studio 2017 geçirdikten, yeni C++ özelliklerden yararlanmak için bazı değişiklikler yapmak isteyebilirsiniz. Visual C++ Derleyici geçerli sürümü C++ Standart sonra önceki sürümleri için daha fazla uyumluluğunu bir göz varsa bazı kodlar kodunuzu diğer derleyiciler daha güvenli ve daha kolay taşınabilir hale getirmek için değişikliklerini işletim sistemleri, dikkate almanız gereken olduğundan ve bazı geliştirmeler.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Küçük ve basit Windows Masaüstü uygulama karalama olması ve dönüştürmek sabit değildi. Çok sayıda küçük, basit uygulamaları kolayca yeni sürüme dönüştürün.  Daha fazla kod satır sayısını, modern mühendislik standartları kadar olmayabilir eski eski kod ile daha karmaşık uygulamalar için birden çok projeye ve kitaplıkları, özel derleme adımları veya karmaşık komut dosyalı otomatik derlemeler için yükseltmek için daha uzun sürer. Devam etmek [sonraki örnek](../porting/porting-guide-com-spy.md), COM Spy adlı ATL/COM uygulama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıma ve yükseltme: örnekler ve örnek olay incelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Sonraki örnek: COM Spy](../porting/porting-guide-com-spy.md)

---
description: 'Daha fazla bilgi edinin: taşıma Kılavuzu: MFC karalama'
title: 'Taşıma Kılavuzu: MFC Scribble'
ms.date: 10/23/2019
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
ms.openlocfilehash: 46fac5ceaeadd803ff30f2fa3f8e7723d7d6f6f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322705"
---
# <a name="porting-guide-mfc-scribble"></a>Taşıma Kılavuzu: MFC Scribble

Bu konu, Visual Studio 'nun eski sürümlerinde Visual Studio 2017 ' ye oluşturulan Visual Studio C++ projeleri için yükseltme yordamına yol gösteren birkaç konunun ilk kavramından biridir. Bu konular, çok basit bir projeden başlayarak ve biraz daha karmaşık olanlara geçerek yükseltme işlemini örnek olarak sunar. Bu konu başlığında, belirli bir proje için yükseltme sürecinde, MFC karalama ile çalışacağız. C++ projeleri için yükseltme işlemine temel bir giriş olarak uygundur.

Visual Studio 'nun her sürümü, Visual Studio 'nun eski bir sürümünden daha yeni bir sürümden kod taşımayı karmaşık hale getirebilecek olası uyumsuzluklar sunar. Bazen gerekli değişiklikler kodunuzda bulunur, bu nedenle kodunuzu yeniden derlemeniz ve güncelleştirmeniz gerekir, bazen gerekli değişiklikler proje dosyaları için de gereklidir. Visual Studio 'nun önceki bir sürümüyle oluşturulmuş bir projeyi açtığınızda, Visual Studio otomatik olarak bir proje veya çözümün en son sürüme güncelleştirilmesini isteyip istemediğinizi sorar. Bu araçlar genellikle yalnızca proje dosyalarını yükseltir; Bunlar, kaynak kodunuzu değiştirmez.

## <a name="mfc-scribble"></a>MFC Scribble

MFC karalama, Visual C++ birçok farklı sürümünde bulunan iyi bilinen bir örnektir. MFC 'nin temel özelliklerinden bazılarını gösteren basit bir çizim uygulamasıdır. Hem yönetilen hem de yerel kod sürümleri dahil olmak üzere çeşitli sürümleri mevcuttur. Bu örnekte, Visual Studio 2005 ' den yerel kodda eski bir karalama sürümü bulduk ve Visual Studio 2017 ' de açıldı.

Yükseltmeyi denemeden önce, Windows masaüstü iş yükünün yüklü olduğundan emin olun. Visual Studio yükleyicisi 'ni açın (vs_installer.exe). Yükleyiciyi açmak için bir yol, **Dosya**  >  **Yeni proje** ' yi seçmek ve **Açık Visual Studio yükleyicisi** görene kadar yüklü şablonlar listesinin altına kaydırmanız. Yükleyiciyi açtıktan sonra, tüm kullanılabilir iş yüklerini görürsünüz. **Windows Masaüstü** iş yükü kutusu seçili değilse, bunu seçip pencerenin alt kısmındaki **Değiştir** düğmesine tıklayın.

Sonra, tüm çözümü ve tüm içeriğini yedekleyin.

Son olarak, çözümü Visual Studio 'nun en son sürümünde açın ve sihirbazın projeyi dönüştürmesini bekleyin.

`/Upgrade`Projelerinizi yükseltmek için Sihirbazı kullanmak yerine, komut satırında devenv ' i de çalıştırabileceğinizi unutmayın. Bkz. [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe). Bu, çok sayıda projenin yükseltme işlemini otomatikleştirmede yararlı olabilir.

### <a name="step-1-converting-the-project-file"></a>Adım 1. Proje dosyası dönüştürülüyor

Visual Studio 'da eski bir proje dosyası açtığınızda, Visual Studio proje dosyasını kabul ettiğimiz en son sürüme dönüştürmek için teklifler sunar. Aşağıdaki iletişim kutusu görüntülendü:

![Proje ve çözüm değişikliklerini gözden geçirme](../porting/media/scribbleprojectupgrade.PNG "Proje ve çözüm değişikliklerini gözden geçirme")

Itanium hedefinin kullanılamadığı ve dönüştürülmeyeceği konusunda bize bildirimde bulunmak için bir hata oluştu.

```Output
Platform 'Itanium' is missing from this project. All the configurations and their file configuration settings specific to this platform will be ignored. If you want this platform converted, please make sure you have the corresponding platform installed under '%vctargetpath%\platforms\Itanium'.Continue to convert this project without this platform?
```

Önceki karalama projesinin oluşturulduğu zamanda, Itanium önemli bir hedef platformudur. Windows platformu artık Itanium 'yi desteklemiyor, bu nedenle Itanium platformunu desteklemeye gerek kalmadan devam etmeyi seçtik.

Daha sonra Visual Studio, eski proje dosyası ile ilgili tüm sorunları listeleyerek bir geçiş raporu görüntülendi.

![Yükseltme raporu](../porting/media/scribblemigrationreport.PNG "Yükseltme raporu")

Bu durumda, sorunlar tüm uyarılardır ve Visual Studio proje dosyasında uygun değişiklikleri yaptı. Projenin en büyük farkı, yapı aracının VCBuild 'den MSBuild 'e değiştiği bir kaygıdır. Bu değişiklik ilk olarak Visual Studio 2010 ' de tanıtılmıştı. Diğer değişiklikler, proje dosyasının kendisindeki öğelerin sırasını yeniden düzenleme içerir. Bu basit proje için daha fazla dikkat etmeniz gereken sorun yok.

### <a name="step-2-getting-it-to-build"></a>Adım 2. Oluşturmaya alma

Derlemeden önce, proje sisteminin hangi derleyici sürümünü kullandığını bilmemiz için platform araç takımını denetliyoruz. Proje Özellikleri iletişim kutusunda, **yapılandırma özellikleri** altında, **genel** kategorisinde, **platform araç takımı** özelliğine bakın. Visual Studio sürümünü ve bu örnekte, araçların Visual Studio 2017 sürümü için v141 olan platform Aracı sürüm numarasını içerir. Özgün olarak Visual Studio 2010, 2012, 2013 veya 2015 ile derlenen bir projeyi dönüştürdüğünüzde, araç takımı en son araç takımını otomatik olarak güncellenmez.

Anahtarı Unicode 'a getirmek için, projenin özelliklerini açın, **yapılandırma özellikleri** altında **genel** bölümünü seçin ve **karakter kümesi** özelliğini bulun. Bunu, **birden çok baytlık karakter kümesini** **Unicode karakter kümesi kullanacak** şekilde değiştirin. Bu değişikliğin etkisi artık _UNICODE ve UNICODE makrolarının tanımlandığından ve _MBCS olmadığından, **komut satırı** özelliğindeki **C/C++** kategorisi altındaki Özellikler iletişim kutusunda doğrulayabilirler.

```Output
/GS /analyze- /W4 /Zc:wchar_t /Zi /Gm- /Od /Fd".\Debug\vc141.pdb" /Zc:inline /fp:precise /D "_AFXDLL" /D "WIN32" /D "_DEBUG" /D "_WINDOWS" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX /Zc:forScope /Gd /Oy- /MDd /Fa".\Debug\" /EHsc /nologo /Fo".\Debug\" /Fp".\Debug\Scribble.pch" /diagnostics:classic
```

Karalama projesi Unicode karakterlerle derlemek üzere ayarlanmamış olsa da, karakter yerine TCHAR ile zaten yazılmıştır, bu nedenle gerçekte değiştirilmeleri gerekmez. Proje Unicode karakter kümesiyle başarıyla oluşturulur.

Şimdi Çözümü derleyin. Çıkış penceresinde derleyici, _WINNT32_WINNT tanımlanmadığı konusunda bize söyler:

```Output
_WIN32_WINNT not defined. Defaulting to _WIN32_WINNT_MAXVER (see WinSDKVer.h)
```

Bu bir uyarı değildir ve bir Visual Studio C++ projesi yükseltilirken çok yaygın bir hatadır. Bu, uygulamamız üzerinde hangi en düşük Windows sürümünün çalışacağını tanımlayan bir makrodur. Uyarıyı yok saydığımızda, geçerli Windows sürümü anlamına gelen _WIN32_WINNT_MAXVER varsayılan değeri kabul ediyoruz. Olası değerler tablosu için bkz. [Windows üst bilgilerini kullanma](/windows/win32/WinProg/using-the-windows-headers). Örneğin, bunu Vista 'dan herhangi bir sürümde çalışacak şekilde ayarlayabiliriz.

```cpp
#define _WIN32_WINNT _WIN32_WINNT_VISTA
```

Kod, bu makroyla belirttiğiniz Windows sürümünde kullanılamayan Windows API 'sinin parçalarını kullanıyorsa, bunu bir derleyici hatası olarak görmeniz gerekir. Karalama kodu söz konusu olduğunda, bir hata yoktur.

### <a name="step-3-testing-and-debugging"></a>3. Adım Test etme ve hata ayıklama

Test paketi yok, bu nedenle uygulamayı yalnızca kullanıcı arabiriminden el ile test ettik. Hiçbir sorun gözlemlenmedi.

### <a name="step-4-improve-the-code"></a>4. Adım: Kodu geliştirme

Artık Visual Studio 2017 ' ye geçirdiniz, yeni C++ özelliklerinden yararlanmak için bazı değişiklikler yapmak isteyebilirsiniz. C++ derleyicisinin geçerli sürümü daha sonra C++ standart ve önceki sürümleri için çok daha uyumlu. bu nedenle, kodunuzu daha güvenli hale getirmek için bazı kod değişiklikleri yapmanız ve diğer derleyiciler ve işletim sistemlerine daha fazla taşınabilir, bazı geliştirmeler göz önünde bulundurmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

Karalama küçük ve basit bir Windows masaüstü uygulamasıdır ve dönüştürme zor değildir. Birçok küçük, basit uygulama yeni sürüme kolayca kolayca dönüştürülür.  Daha karmaşık uygulamalar için, çok daha fazla kod satırı, modern mühendislik standartları, birden fazla proje ve kitaplık, özel derleme adımı veya karmaşık komut dosyalı otomatik derlemeler için daha fazla eski kod, yükseltmenin yükseltilmesi daha fazla zaman alır. COM Spy adlı bir ATL/COM uygulaması olan bir [sonraki örnekle](../porting/porting-guide-com-spy.md)devam edin.

## <a name="see-also"></a>Ayrıca bkz.

[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Sonraki örnek: COM Spy](../porting/porting-guide-com-spy.md)

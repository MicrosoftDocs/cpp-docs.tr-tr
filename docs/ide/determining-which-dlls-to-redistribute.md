---
title: Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme
ms.date: 06/08/2018
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
ms.openlocfilehash: fdca832810312d2f36697da8fbaac539c5ce951c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452604"
---
# <a name="determining-which-dlls-to-redistribute"></a>Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme

Visual Studio tarafından sağlanan kitaplığı DLL'ler kullanan bir uygulama oluşturduğunuzda, uygulamanızın kullanıcılarının uygulamayı çalıştırmak için kendi bilgisayarlarında bu DLL'leri de olmalıdır. Çoğu kullanıcı büyük olasılıkla Visual Studio'nun yüklü olmadığından, bu DLL'leri için bunları sağlamanız gerekir. Visual Studio kullanılabilir hale getirir bu dll olarak *yeniden dağıtılabilir dosyaları* , uygulama Yükleyicinizle içerebilir.

Yükleyicinizle birlikte yeniden dağıtılabilir DLL'lerinin dahil daha kolay hale getirmek için bunlar bağımsız olarak kullanılabilir *yeniden dağıtılabilir paketleri*. Bu, bir kullanıcının bilgisayarına yeniden dağıtılabilir dosyalarını yüklemek için merkezi dağıtım kullanmaktadır mimariye özel yürütülebilir dosyalar. Örneğin, vcredist\_x86.exe x86 için 32-bit kitaplıklarını yükler bilgisayarlar, vcredist\_x64.exe x64 için 32-bit ve 64-bit kitaplıklarını yükler bilgisayarlar ve vcredist\_ARM.exe kitaplıkları için ARM yükler bilgisayarlar. Microsoft bu kitaplıklar bağımsız olarak güncelleştirmek için Windows Update hizmeti kullanabileceğinizden merkezi dağıtım öneririz. Visual Studio yüklemenizin kopyalama ek olarak, geçerli yeniden dağıtılabilir paketleri indirmek için mevcuttur. En son desteklenen için yeniden dağıtılabilir paketleri hem geçerli hem de eski araç takımları bağlantıları için bkz [Visual C++ indirmeleri en son desteklenen](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads). Arama yaparak belirli önceki sürümleri yeniden dağıtılabilir paketleri bulunabilir [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?LinkId=158431) "Visual C++ yeniden dağıtılabilir paketleri" için.

Dağıttığınız yeniden dağıtılabilir paketinin ana sürüm numarası uygulamanızı oluşturmak için kullanılan Visual Studio araç takımı sürümü ile eşleşmelidir ve alt sürümü aynı olmalıdır veya üzeri. Visual Studio 2017 ve Visual Studio 2015, Visual Studio 2017 yeniden dağıtılabilir dosyaları, 2015 Araç Takımı ' kullanılarak oluşturulmuş uygulamalar tarafından kullanılabilir, yani, uyumlu bir araç takımı sürüm numaralarına sahip. Uyumlu olabilir, ancak 2017 araç takımını kullanılarak oluşturulmuş uygulamalar 2015 yeniden dağıtılabilir dosyaları kullanmaya desteklemez. Yalnızca aynı veya, araç takımı sürümden daha yeni bir yeniden dağıtılabilir paketi kullanarak destekliyoruz.

Yükleyicinizle birlikte yeniden dağıtılabilir DLL'lerinin dahil etmek için başka bir yolu *birleştirme modülleri*. Bu Microsoft Installer modülleri bulunan ve uygulama Yükleyicinizle tarafından yüklenmiş. Yeniden dağıtılabilir DLL'lerinin ilişkin birleştirme modülleri, Visual Studio yükleme dizini altında bulunur \\VC\\Redist\MSVC\\*sürüm*\\MergeModules\\ . Bu dosyalar bulunan Visual Studio'nun önceki sürümlerinde, \\Program dosyaları veya \\Common Files (x86) Program Files dizininde\\birleştirme modülleri alt. Bu dosyalar kullanımı hakkında daha fazla bilgi için bkz. [birleştirme modüllerini kullanarak bileşenleri yeniden dağıtma](../ide/redistributing-components-by-using-merge-modules.md).

Bağımsız yeniden dağıtılabilir DLL'lerinin Visual Studio yüklemenizde de dahil edilir. Varsayılan olarak, Visual Studio yükleme dizininde yüklendiklerinde \\VC\\Redist\\MSVC\\*sürüm* klasör. *Sürüm* sayıları yeniden dağıtılabilir dosyaları tek ortak bir dizi farklı bir alt yapı numaralarını temsil. Herhangi bir kitaplık DLL dosyası, yeniden dağıtılabilir paketi veya bu dizinlerde bulunan birleştirme modülü en son sürümünü kullanın. Uygulamanız ile aynı dizinde yükleyerek yerel dağıtımı için bu kitaplıkları kullanabilir. Güncelleştirmeleri, dağıtılan uygulamalarınıza teslim sorumlu kolaylaştırır çünkü yerel dağıtım önerilmemektedir. Yeniden dağıtılabilir paketleri kullanarak merkezi dağıtım tercih edilir.

Hangi DLL'leri uygulamanızla yeniden dağıtmanıza gerek belirlemek için uygulamanızın bağlı olduğu DLL'lerin bir listesini toplayın. Bu normalde bağlayıcıya kitaplık girişlerini alma olarak listelenir. Vcruntime ve evrensel C çalışma zamanı kitaplığı (UCRT), gibi belirli kitaplıkları, varsayılan olarak dahil edilir. Uygulamanız veya onun bağımlılıklarından biri dinamik olarak bir DLL'yi LoadLibrary kullanıyorsa, bu DLL bağlayıcı için girişlerinde listelenmeyebilir. Dinamik olarak yüklenen DLL'lerin listesini toplamanın bir yolu olan bağımlılık Denetçisi'ni (depends.exe), uygulamanızı çalıştırmak için açıklandığı [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Ne yazık ki, bu araç, güncel değildir ve belirli DLL'ler bulunamıyor bildirebilir.

Bağımlılıklar listesine sahip olduğunuzda Microsoft Visual Studio yükleme dizininde bulunan Redist.txt dosyasındaki bağlantılı liste ya da "" Dağıtılabilir kod dosyaları"bölümünde başvuruda bulunulan REDIST listesi" yeniden dağıtılabilir DLL'lerin bu karşılaştırın Microsoft Yazılımı Lisans koşulları Visual Studio kopyası için. Visual Studio 2017 için bkz. [Microsoft Visual Studio 2017 (içerir yardımcı programlar, genişletilebilirlik ve BuildServer Dosyaları) için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?linkid=823098). Visual Studio 2015 için bkz: [Microsoft Visual Studio 2015 ve Microsoft Visual Studio 2015 SDK'sı (içerir yardımcı programları ve BuildServer Dosyaları) için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?linkid=799794). Visual Studio 2013 için liste çevrimiçi kullanılabilir [Microsoft Visual Studio 2013 ve Microsoft Visual Studio 2013 SDK için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?LinkId=313603).

Visual Studio 2015 önce Visual Studio sürümlerinde, C çalışma zamanı kitaplığı (CRT) yeniden dağıtılabilir DLL, msvc olarak dahil edilen*sürüm*.dll. Visual Studio 2015'ten başlayarak, CRT işlevleri vcruntime ve UCRT yeniden. UCRT Windows 10, Windows Update tarafından yönetilen bir sistem bileşeninde sunulmuştur. Tüm Windows 10 işletim sistemlerinde kullanılabilir. Uygulamanızı önceki işletim sistemlerini dağıtmak için de UCRT yeniden dağıtmanız gerekebilir. UCRT herhangi bir sürümü zaten yüklü değilse yalnızca işletim sistemlerinde Windows 10'dan daha önce yüklenmişse, Visual Studio yeniden dağıtılabilir dosyaları dahil ve yalnızca UCRT'ın eski bir sürümü. Alt düzey sistemleri UCRT Microsoft Sistem Güncelleştirme paketi olarak yüklenebilir bir sürümü için bkz: [Windows 10 Evrensel C çalışma zamanı](https://www.microsoft.com/download/details.aspx?id=48234) Microsoft Download Center'daki.

Visual Studio'ya dahil olan dosyaların tümünü yeniden dağıtamazsınız; yalnızca Redist.txt'de veya çevrimiçi "REDIST listesi." Belirtilen dosyaları yeniden dağıtmak için izin verilir Uygulamaların hata ayıklama sürümleri ve çeşitli Visual C++ hata ayıklama DLL'leri yeniden dağıtılamaz. Daha fazla bilgi için [dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md).

Aşağıdaki tablo uygulamanızın bağımlı olabileceği Visual C++ DLL'lerini bazılarını açıklar.

|Visual C++ Kitaplığı|Açıklama|Uygulandığı öğe:|
|--------------------------|-----------------|----------------|
|vcruntime*sürüm*.dll|Yerel kod için çalışma zamanı kitaplığı.|Normal C ve C++ dil başlatma ve sonlandırma hizmetleri kullanan uygulamalar.|
|vccorlib*sürüm*.dll|Yönetilen kod için çalışma zamanı kitaplığı.|Yönetilen kod için C++ dil hizmetleri kullanan uygulamalar.|
|msvcp*sürüm*.dll ve msvcp*sürüm*_*dotnumber*.dll|Yerel kod için C++ Standart Kitaplığı.|Kullanan uygulamalar [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md).|
|concrt*sürüm*.dll|Yerel kod için eşzamanlılık çalışma zamanı kitaplığı.|Kullanan uygulamalar [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).|
|MFC*sürüm*.dll|(MFC) kitaplığı Microsoft Foundation sınıfları.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md).|
|MFC*sürüm* *dil*.dll|Kitaplık kaynakları (MFC) Microsoft Foundation sınıfları.|MFC için belirli bir dil kaynakları kullanan uygulamalar.|
|MFC*sürüm*u.dll|Unicode desteği olan MFC Kitaplığı.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ve Unicode desteği gerektirir.|
|mfcmifc80.dll|MFC yönetilen arabirimler kitaplığı.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ile [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index).|
|mfcm*sürüm*.dll|MFC yönetilen kitaplığı.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ile [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index).|
|mfcm*sürüm*u.dll|MFC yönetilen kitaplığı Unicode desteği olan.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ile [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index) ve Unicode desteği gerektirir.|
|vcamp*sürüm*.dll|Yerel kod için AMP kitaplığı.|Kullanan uygulamalar [C++ AMP Kitaplığı](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) kod.|
|vcomp*sürüm*.dll|OpenMP kitaplık yerel kod.|Kullanan uygulamalar [C++ OpenMP kitaplık](../parallel/openmp/openmp-in-visual-cpp.md) kod.|

> [!NOTE]
> Artık Active Template Library ayrı bir DLL olarak yeniden dağıtmanız gerekmez. Üst bilgiler ve statik kitaplıkta işlevselliği taşındı.

Bu DLL'leri uygulamanızla birlikte yeniden dağıtma hakkında daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md). Örnekler için bkz [Dağıtım örnekleri](../ide/deployment-examples.md).

Genellikle, işletim sisteminin bir parçası olduklarından, sistem DLL'lerini yeniden dağıtmanız gerekmez. Ancak, özel durumlar olabilir, örneğin, uygulamanızın Microsoft işletim sistemlerinin bazı sürümlerinde çalışacağı. Bu durumda, ilgili lisans koşullarını mutlaka okuyun. Ayrıca, sistem DLL'lerini hizmet paketleri, Windows Update aracılığıyla ya da Microsoft'un sunduğu yeniden dağıtılabilir paketleri kullanarak almayı deneyin.

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım Yöntemi Seçme](../ide/choosing-a-deployment-method.md)

[Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)

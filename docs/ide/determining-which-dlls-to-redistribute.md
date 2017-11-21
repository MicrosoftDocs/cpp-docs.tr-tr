---
title: "Hangi DLL'lerin yeniden dağıtılacağını belirleme | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae47ec92ecea46aba5f0e1bf144a34fd5532af9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="determining-which-dlls-to-redistribute"></a>Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme

Visual Studio tarafından sağlanan kitaplığı DLL'ler kullanan bir uygulama oluşturduğunuzda, uygulamanızın kullanıcıların bilgisayarlarında uygulamayı çalıştırmak için de bu DLL'ler olması gerekir. Kullanıcıların çoğunun büyük olasılıkla Visual Studio'nun yüklü olmadığı için bu DLL'ler için bunları sağlamanız gerekir. Visual Studio kullanılabilir hale getirir bu dll olarak *yeniden dağıtılabilir dosyaları* , uygulama Yükleyicinizle içerebilir.

Yeniden dağıtılabilir DLL'leri, yükleyici ile dahil kolaylaştırmak için bağımsız olarak kullanılabilir olmaları *yeniden dağıtılabilir paketleri*. Bu, bir kullanıcının bilgisayarda yeniden dağıtılabilir dosyalarını yüklemek için merkezi dağıtım kullanın mimarisi özgü yürütülebilir dosyalar. Örneğin, vcredist\_x86.exe yükler x86 için 32-bit kitaplıkları bilgisayarlar, vcredist\_x64.exe x64 için 32-bit ve 64-bit kitaplıkları yükler bilgisayarlar ve vcredist\_ARM.exe kitaplıkları için ARM yükler bilgisayarlar. Microsoft bu kitaplıklar bağımsız olarak güncelleştirmek için Windows Update hizmeti kullanabileceğinizden merkezi dağıtım öneririz. Visual Studio yüklemenizin kopyada ek olarak, geçerli yeniden dağıtılabilir paketlerini indirmek için kullanılabilir olan [VisualStudio.com/Downloads](https://www.visualstudio.com/downloads/) diğer araçlar ve çerçeveleri bölümünde.

Dağıttığınız yeniden dağıtılabilir paketinin ana sürüm numarası, uygulamanızı oluşturmak için kullanılan Visual Studio araç takımı sürümü aynı olmalıdır. Visual Studio 2017 ve Visual Studio 2015, Visual Studio 2015 araç setini kullanarak oluşturulan uygulamaları tarafından yeniden dağıtılabilir dosyaları kullanılabilir 2017 anlamına gelir uyumlu araç takımı sürüm numarasına sahip. Uyumlu olabilir, ancak 2017 araç takımı kullanılarak oluşturulan uygulamaları 2015 redistributable dosyalarında kullanılmasını desteklemez. Aynı veya araç takımı sürümden daha yeni bir yeniden dağıtılabilir paketi kullanarak yalnızca destekler. En son desteklenen yeniden dağıtılabilir paketler için eski toolsets bağlantıları için bkz: [en son Visual C++ yüklemeleri desteklenen](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). Yeniden dağıtılabilir paketleri belirli önceki sürümlerini arayarak bulunabilir [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?LinkId=158431) "Visual C++ yeniden dağıtılabilir paketler" için.

Yeniden dağıtılabilir DLL'leri, yükleyici ile eklemek için başka bir yolu kullanmaktır *birleştirme modülleri*. Bu Microsoft Installer modüller dahil ve uygulama yükleyicisi tarafından yüklenen. Birleştirme modülleri yeniden dağıtılabilir DLL'ler için Visual Studio yükleme dizini altında bulunur \\VC\\Redist\MSVC\\*sürüm*\\MergeModules\\ . Bu dosyaları bulunan Visual Studio'nun önceki sürümleri, \\Program Files veya \\Program Files (x86) Common Files dizininde\\birleştirme modülleri alt. Bu dosyalar kullanımı hakkında daha fazla bilgi için bkz: [birleştirme modüllerini kullanarak bileşenleri yeniden dağıtma](../ide/redistributing-components-by-using-merge-modules.md).

Tek tek yeniden dağıtılabilir DLL'leri de Visual Studio yüklemenizin dahil edilir. Varsayılan olarak, Visual Studio yükleme dizininde yüklendikleri \\VC\\Redist\\MSVC\\*sürüm* klasör. *Sürüm* numaralarını yeniden dağıtılabilir dosyaları tek ortak bir dizi farklı bir alt yapı numaralarını temsil. Herhangi bir kitaplık DLL dosyası, yeniden dağıtılabilir paketi veya birleştirme modülü bu dizinlerde bulunan en son sürümünü kullanın. Uygulamanız ile aynı dizinde yükleyerek bu kitaplıklar yerel dağıtım için kullanabilir. Dağıtılmış uygulamalarınız için güncelleştirmeler gönderiliyor sorumlu kolaylaştırır ki yerel dağıtım önerilmez. Yeniden dağıtılabilir paketleri kullanılarak merkezi dağıtım tercih edilir.

İle uygulamanızı yeniden dağıtmanıza gerek hangi DLL'lerin belirlemek için uygulamanızın bağımlı DLL'lerin listesini toplayın. Bunlar normalde bağlayıcı kitaplık girişleri içe aktarırken listelenmiştir. Vcruntime ve evrensel C çalışma zamanı kitaplığı (UCRT), gibi belirli kitaplıkları, varsayılan olarak dahil edilir. Uygulamanızı veya bağımlılıklarından biri LoadLibrary DLL dinamik olarak yüklemek için kullanılıyorsa, bu DLL bağlayıcı girişleri içinde listelenen değil. Dinamik olarak yüklenen DLL'leri listesi toplamak için bir yoldur bağımlılık bekçisi (depends.exe) uygulamanızı üzerinde çalıştırmak için açıklandığı gibi [bir Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Ne yazık ki, bu aracı eskidir ve belirli DLL'ler bulunamıyor bildirebilir.

Bağımlılıklar listesine sahip olduğunuzda Microsoft Visual Studio yükleme dizininde bulunan Redist.txt dosyasındaki bağlı listesi ya da ""Dağıtılabilir kod dosyaları"bölümünde başvurulan REDIST" yeniden dağıtılabilir DLL'lerin listesini bu karşılaştırın Microsoft Yazılımı Lisans koşulları Visual Studio kopyası için. Visual Studio 2017 için bkz: [Microsoft Visual Studio 2017 (yardımcı programları içerir, genişletilebilirlik ve BuildServer Dosyaları) için dağıtılabilir kod](http://go.microsoft.com/fwlink/?LinkId=823098). Visual Studio 2015 için bkz: [Microsoft Visual Studio 2015 ve Microsoft Visual Studio 2015 SDK (içerir yardımcı programları ve BuildServer Dosyaları) için dağıtılabilir kod](http://go.microsoft.com/fwlink/?LinkId=799794). Visual Studio 2013 için listenin çevrimiçi kullanılabilir [Microsoft Visual Studio 2013 ve Microsoft Visual Studio 2013 SDK için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?LinkId=313603).

C çalışma zamanı kitaplığı (CRT) Visual Studio 2015 önce Visual Studio sürümlerinde, bir yeniden dağıtılabilir DLL'de msvc olarak dahil*sürüm*.dll. Visual Studio 2015'ten başlayarak, CRT işlevlerde vcruntime ve UCRT halinde bulunanad. UCRT Windows 10, Windows Update tarafından yönetilen bir sistem bileşeni sunulmuştur. Tüm Windows 10 işletim sistemlerinde kullanılabilir. Uygulamanızı daha eski işletim sistemlerini dağıtmak için UCRT de yeniden dağıtmanız gerekebilir. UCRT herhangi bir sürümü zaten yüklüyse, yalnızca işletim sistemlerinde Windows 10'dan önceki yüklenir, Visual Studio yeniden dağıtılabilir dosyaları dahil ve yalnızca UCRT eski bir sürümü. Alt düzey sistemler için UCRT Microsoft Sistem güncelleştirmesi paketi olarak yüklenebilen bir sürümü için bkz: [Windows 10 Universal C çalışma zamanı](https://www.microsoft.com/en-us/download/details.aspx?id=48234) Microsoft Download Center'da.

Visual Studio'da bulunan dosyaların tamamını dağıtamazsınız; Redist.txt'e veya çevrimiçi "listesidir." Belirtilen dosyaları yeniden dağıtmak için yalnızca izin verilen Uygulamaların hata ayıklama sürümleri ve çeşitli Visual C++ hata ayıklama DLL'leri dağıtılamaz. Daha fazla bilgi için bkz: [dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md).

Aşağıdaki tabloda, uygulamanızın bağlı Visual C++ DLL'leri bazıları açıklanmaktadır.

|Visual C++ Kitaplığı|Açıklama|Uygulandığı öğe:|
|--------------------------|-----------------|----------------|
|vcruntime*sürüm*.dll|Yerel kod için çalışma zamanı kitaplığı.|Normal C ve C++ dili başlatma ve sonlandırma hizmetleri kullanan uygulamalar.|
|vccorlib*sürüm*.dll|Yönetilen kod için çalışma zamanı kitaplığı.|Yönetilen kod için C++ dili hizmetleri kullanan uygulamalar.|
|msvcp*sürüm*.dll|Yerel kod için C++ Standart Kitaplığı.|Kullanan uygulamalar [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md).|
|concrt*sürüm*.dll|Yerel kod eşzamanlılık çalışma zamanı kitaplığı.|Kullanan uygulamalar [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).|
|MFC*sürüm*.dll|Microsoft Foundation (MFC) kitaplığı sınıflarını kullanın.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md).|
|MFC*sürüm* *dil*.dll|Microsoft Foundation (MFC) kitaplık kaynaklarını sınıfları.|MFC için belirli bir dil kaynakları kullanan uygulamalar.|
|MFC*sürüm*u.dll|MFC Kitaplığı Unicode desteğine sahip.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ve Unicode desteği gerektirir.|
|mfcmifc80.dll'ye|MFC yönetilen arabirimler kitaplığı.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ile [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index).|
|mfcm*sürüm*.dll|MFC yönetilen kitaplığı.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ile [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index).|
|mfcm*sürüm*u.dll|MFC yönetilen kitaplığı Unicode desteğine sahip.|Kullanan uygulamalar [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) ile [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index) ve Unicode desteği gerektirir.|
|vcamp*sürüm*.dll|Yerel kod için AMP kitaplığı.|Kullanan uygulamalar [C++ AMP Kitaplığı](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) kodu.|
|vcomp*sürüm*.dll|Yerel kod OpenMP kitaplık.|Kullanan uygulamalar [C++ OpenMP kitaplık](../parallel/openmp/openmp-in-visual-cpp.md) kodu.|

> [!NOTE]
> Artık etkin Şablon Kütüphanesi ayrı bir DLL olarak yeniden dağıtmanız gerekir. Üstbilgiler ve bir statik kitaplık işlevselliğini taşındı.

Yeniden bu DLL'lerini uygulamanız ile dağıtma hakkında daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md). Örnekler için bkz: [Dağıtım örnekleri](../ide/deployment-examples.md).

Genellikle, işletim sisteminin bir parçası olduğundan sistem DLL'leri yeniden dağıtmanız gerekmez. Ancak, özel durumlar olabilir, örneğin, uygulamanız Microsoft işletim sistemlerinin bazı sürümlerinde çalıştırdığınızda. Bu durumda, karşılık gelen Lisans Koşulları'nı okuduğunuzdan emin olun. Ayrıca, Windows Update, hizmet paketleri aracılığıyla veya Microsoft tarafından kullanılabilir hale yeniden dağıtılabilir paketleri kullanılarak DLL'lerini sistem almayı deneyin.

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md)

[Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)

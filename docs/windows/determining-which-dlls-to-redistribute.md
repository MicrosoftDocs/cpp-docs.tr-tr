---
description: "Daha fazla bilgi edinin: hangi dll 'Lerin yeniden dağıtılacağını belirleme"
title: Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme
ms.date: 07/15/2019
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
ms.openlocfilehash: 016351a6d204c71cfef516862c9b57bebafcc1a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329398"
---
# <a name="determining-which-dlls-to-redistribute"></a>Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme

Visual Studio tarafından sağlanan kitaplık dll 'Lerini kullanan bir uygulama oluşturduğunuzda, uygulamanızın kullanıcıları, uygulamanın çalışması için kendi bilgisayarlarında bu DLL 'Leri de içermelidir. Çoğu kullanıcı büyük olasılıkla Visual Studio 'nun yüklü olmadığı için bu DLL 'Leri bu DLL 'Ler için sağlamanız gerekir. Visual Studio, bu DLL 'Leri uygulama yükleyicinizin içinde yer alan *yeniden dağıtılabilir dosyalar* olarak sunar.

Yeniden dağıtılabilir DLL 'Leri yükleyicinizle birlikte eklemeyi kolaylaştırmak için, tek başına *yeniden dağıtılabilir paketler* olarak kullanılabilir. Bunlar, bir kullanıcının bilgisayarına yeniden dağıtılabilir dosyaları yüklemek için merkezi dağıtım kullanan mimariye özgü yürütülebilir dosyalardır. Örneğin, VCRedist \_x86.exe hem x86 hem de x64 bilgisayarlarda 32 bitlik kitaplıkları yüklerse, vcredist \_x64.exe x64 bilgisayarlar için 64 bit kitaplıklarını ve VCREDIST \_ARM.exe ARM bilgisayarları için kitaplıklarını yüklerse. Microsoft bu kitaplıkları bağımsız olarak güncelleştirmek için Windows Update hizmetini kullanabildiğinden merkezi dağıtım yapmanızı öneririz. Visual Studio yüklemenizin kopyasına ek olarak, geçerli yeniden dağıtılabilir paketler indirilebilir. Hem geçerli hem de eski araç kümeleri için desteklenen en son yeniden dağıtılabilir paketlere bağlantılar için [desteklenen en son Visual C++ İndirmeleri](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)bölümüne bakın. Yeniden dağıtılabilir paketlerin belirli bir önceki sürümleri, Visual C++ "yeniden dağıtılabilir paketler" için [Microsoft Indirme merkezi](https://go.microsoft.com/fwlink/p/?LinkId=158431) ' ni arayarak bulunabilir.

Dağıttığınız yeniden dağıtılabilir paketin ana sürüm numarası, uygulamanızı oluşturmak için kullanılan Visual Studio araç takımının sürümüyle eşleşmelidir ve ikincil sürüm aynı veya daha yüksek olmalıdır. Visual Studio 2017 ve Visual Studio 2015, uyumlu araç kümesi sürüm numaralarına sahiptir; bu, Visual Studio 2017 yeniden dağıtılabilir dosyaları, 2015 araç kümesi kullanılarak oluşturulan uygulamalar tarafından kullanılabilir. Uyumlu olsa da, 2017 araç kümesi kullanılarak oluşturulan uygulamalarda 2015 yeniden dağıtılabilir dosyaları kullanmayı desteklemeiyoruz. Yalnızca araç seti sürümünüzle aynı veya daha yeni olan yeniden dağıtılabilir bir paket kullanmayı destekliyoruz.

Yeniden dağıtılabilir DLL 'Leri yükleyicinizle birlikte eklemenin başka bir yolu da *birleştirme modüllerini* kullanmaktır. Bu Microsoft yükleyicisi modülleri, uygulama yükleyicinizin içinde bulunur ve yüklenir. Yeniden dağıtılabilir DLL 'Ler için birleştirme modülleri, \\ VC \\ Redist\MSVC \\ *Sürüm* \\ mergemodules altındaki Visual Studio yükleme dizininizde bulunur \\ . Visual Studio 'nun önceki sürümlerinde, bu dosyalar \\ \\ ortak bir dosya \\ birleştirme modülleri alt dizininde program dosyalarınızda veya Program Files (x86) dizininde bulunur. Bu dosyaların kullanımı hakkında daha fazla bilgi için bkz. [birleştirme modüllerini kullanarak bileşenleri yeniden dağıtma](redistributing-components-by-using-merge-modules.md).

Tek başına yeniden dağıtılabilir DLL 'Ler, Visual Studio yüklemenize de dahildir. Varsayılan olarak, \\ VC \\ Redist \\ MSVC \\ *Sürüm* klasöründeki Visual Studio yükleme dizinine yüklenir. *Sürüm* numaraları, tek bir ortak yeniden dağıtılabilir dosyalar kümesinin farklı küçük derleme numaralarını temsil edebilir. Herhangi bir kitaplık DLL dosyası, yeniden dağıtılabilir paket veya bu dizinlerde bulunan birleştirme modülünün en son sürümünü kullanın. Bu kitaplıkları, uygulamanızla aynı dizine yükleyerek yerel dağıtım için kullanabilirsiniz. Dağıtılan uygulamalarınıza güncelleştirme teslim etmekten sorumlu olduğundan, yerel dağıtım yapmanız önerilmez. Yeniden dağıtılabilir paketler kullanılarak merkezi dağıtım tercih edilir.

Uygulamanızla hangi dll 'Leri yeniden dağıtmanız gerektiğini öğrenmek için uygulamanızın bağımlı olduğu dll 'lerin bir listesini toplayın. Bunlar normalde bağlayıcıya kitaplık girişleri içeri aktarma olarak listelenir. Vcruntime ve evrensel C çalışma zamanı kitaplığı (UCRT) gibi bazı kitaplıklar varsayılan olarak dahil edilmiştir. Uygulamanız veya bağımlılıklarından biri bir DLL 'yi dinamik olarak yüklemek için LoadLibrary kullanıyorsa, bu DLL bağlayıcı girişlerinde listelenmeyebilir. Dinamik olarak yüklenen dll 'lerin listesini toplamanın bir yolu, [bir Visual C++ uygulamasının bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md)bölümünde açıklandığı gibi uygulamanızda bağımlılık denetçisi 'ni (depends.exe) çalıştıramaktır. Ne yazık ki bu araç güncel değildir ve belirli dll 'Leri bulamadıklarından rapor verebilir.

Bağımlılıklar listesine sahip olduğunuzda, Microsoft Visual Studio yükleme dizini altında bulunan Redist.txt dosyasına veya Visual Studio kopyanızın Microsoft yazılım lisans koşulları 'nın "dağıtılabilir kod dosyaları" bölümünde belirtilen "yeniden dağıtılabilir DLL 'lerin" yeniden dağıtılabilir DLL 'lerinin "REDıST listesi" bölümüne göre karşılaştırın. Visual Studio 2017 için bkz. [Microsoft Visual Studio 2017 Için dağıtılabilir kod (yardımcı programlar, genişletilebilirlik ve BuildServer dosyalarını içerir)](/visualstudio/productinfo/2017-redistribution-vs). Visual Studio 2015 için bkz. [Microsoft Visual Studio 2015 ve Microsoft Visual Studio 2015 SDK Için dağıtılabilir kod (yardımcı programları ve BuildServer dosyalarını içerir)](/visualstudio/productinfo/2015-redistribution-vs). Visual Studio 2013 için, liste [Microsoft Visual Studio 2013 ve Microsoft Visual Studio 2013 SDK Için dağıtılabilir kod](/visualstudio/productinfo/2013-redistribution-vs)' de çevrimiçi olarak kullanılabilir.

Visual Studio 2015 ' den önceki Visual Studio sürümlerinde, C çalışma zamanı kitaplığı (CRT) MSVC *Version*. dll içinde yeniden DAĞITILABILIR bir dll olarak eklenmiştir. Visual Studio 2015 ' den başlayarak, CRT içindeki işlevler vcruntime ve UCRT 'ye yeniden düzenlenmiş. UıCRT artık Windows 10 ' da Windows Update tarafından yönetilen bir sistem bileşenidir. Bu, tüm Windows 10 işletim sistemlerinde kullanılabilir. Uygulamanızı önceki işletim sistemlerine dağıtmak için UCRT 'yi de yeniden dağıtmanız gerekebilir. UıCRT 'ın erken bir sürümü, yalnızca Windows 10 ' dan önceki işletim sistemlerine yüklenen ve yalnızca UCRT 'nin bir sürümü yüklü değilse, Visual Studio Redistributable dosyalarına dahil edilmiştir. Bir Microsoft Sistem Güncelleştirme paketi olarak alt düzey sistemler için UCRT 'nin yüklenebilir bir sürümü için, Microsoft Indirme merkezi 'nde [Windows 10 Universal C çalışma zamanı](https://www.microsoft.com/download/details.aspx?id=48234) bölümüne bakın.

Visual Studio 'da bulunan tüm dosyaları yeniden dağıtamazsınız; yalnızca Redist.txt veya çevrimiçi "yeniden dağıtım listesi" içinde belirtilen dosyaları yeniden dağıtmanıza izin verilir. Uygulamaların hata ayıklama sürümleri ve çeşitli Visual C++ hata ayıklama dll 'Leri yeniden dağıtılabilir değildir. Daha fazla bilgi için bkz. [dağıtım yöntemi seçme](choosing-a-deployment-method.md).

Aşağıdaki tabloda, uygulamanızın bağlı olabileceği bazı Visual C++ dll 'Ler açıklanmaktadır.

|Visual C++ Kitaplığı|Açıklama|Şunlara uygulanır|
|--------------------------|-----------------|----------------|
|vcruntime *sürümü*. dll|Yerel kod için çalışma zamanı kitaplığı.|Normal C ve C++ dil başlatma ve sonlandırma hizmetlerini kullanan uygulamalar.|
|vccorlib *sürümü*. dll|Yönetilen kod için çalışma zamanı kitaplığı.|Yönetilen kod için C++ dil hizmetlerini kullanan uygulamalar.|
|msvcp *Version*. dll ve msvcp *Sürüm* _ *dotnumber*. dll|Yerel kod için C++ Standart Kitaplığı.|[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)kullanan uygulamalar.|
|ConcRT *sürümü*. dll|Yerel kod için Eşzamanlılık Çalışma Zamanı Kitaplığı.|[Eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md)kullanan uygulamalar.|
|MFC *sürümü*. dll|Microsoft Foundation Sınıfları (MFC) kitaplığı.|[MFC Kitaplığı](../mfc/mfc-desktop-applications.md)kullanan uygulamalar.|
|MFC *Sürüm* *dili*. dll|Microsoft Foundation Sınıfları (MFC) kitaplık kaynakları.|MFC için belirli dil kaynaklarını kullanan uygulamalar.|
|MFC *sürüm* u.dll|Unicode desteği olan MFC Kitaplığı.|[MFC Kitaplığı](../mfc/mfc-desktop-applications.md) kullanan ve Unicode desteği gerektiren uygulamalar.|
|mfcmifc80.dll|MFC yönetilen arabirimler kitaplığı.|[Windows Forms denetimleri](/dotnet/framework/winforms/controls/index)Ile [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) kullanan uygulamalar.|
|MFCM *Sürüm*. dll|MFC yönetilen Kitaplığı.|[Windows Forms denetimleri](/dotnet/framework/winforms/controls/index)Ile [MFC Kitaplığı](../mfc/mfc-desktop-applications.md) kullanan uygulamalar.|
|MFCM *sürüm* u.dll|Unicode desteği olan MFC yönetilen Kitaplığı.|[MFC Kitaplığı](../mfc/mfc-desktop-applications.md) kullanan uygulamalar [Windows Forms denetimlerle](/dotnet/framework/winforms/controls/index) ve Unicode desteği gerektirir.|
|vcamp *sürümü*. dll|Yerel kod için AMP kitaplığı.|[C++ amp kitaplığı](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) kodunu kullanan uygulamalar.|
|vcomp *sürümü*. dll|Yerel kod için OpenMP kitaplığı.|[C++ OpenMP kitaplığı](../parallel/openmp/openmp-in-visual-cpp.md) kodunu kullanan uygulamalar.|

> [!NOTE]
> Artık etkin şablon kitaplığını ayrı bir DLL olarak yeniden dağıtmanız gerekmez. İşlevselliği, üstbilgilere ve statik kitaplığa taşındı.

Bu dll 'Leri uygulamanızla birlikte yeniden dağıtma hakkında daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md). Örnekler için bkz. [dağıtım örnekleri](deployment-examples.md).

Genellikle, işletim sisteminin bir parçası olduklarından sistem dll 'Lerini yeniden dağıtmanız gerekmez. Bununla birlikte, örneğin, uygulamanız Microsoft işletim sistemlerinin birkaç sürümünde çalıştırıldığında özel durumlar olabilir. Bu durumda, ilgili lisans koşullarını okuduğunuzdan emin olun. Ayrıca, Windows Update, hizmet paketleri aracılığıyla ya da Microsoft tarafından sunulan yeniden dağıtılabilir paketleri kullanarak yükseltilen sistem dll 'Lerini almayı deneyin.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Yöntemi Seçme](choosing-a-deployment-method.md)<br/>
[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)

---
title: C++ konsol uygulama projesi derleyip çalıştırma
description: Visual C++ konsol uygulamasında Hello World konsol uyrup çalıştırın
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: d1e92e598b370312730a7c4e208b935a264010bf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749247"
---
# <a name="build-and-run-a-c-console-app-project"></a>C++ konsol uygulama projesi derleyip çalıştırma

Bir C++ konsol uygulaması projesi oluşturdunuz ve kodunuzu girdiniz. Şimdi visual studio içinde inşa edebilir ve çalıştırabilirsiniz. Ardından, komut satırından tek başına bir uygulama olarak çalıştırın.

## <a name="prerequisites"></a>Ön koşullar

- C++ iş yükü yüklü ve bilgisayarınızda çalışan Masaüstü geliştirme ile Visual Studio var. Henüz yüklenmediyse, [Visual Studio'da C++ yükle'deki](vscpp-step-0-installation.md)adımları izleyin.

- Bir "Merhaba, Dünya!" yaratın. ve kaynak kodunu girin. Bu adımı henüz yapmadıysanız, [C++ konsol uyrum uygulaması projesi oluştur'daki](vscpp-step-1-create.md)adımları izleyin.

Visual Studio bu şekilde görünüyorsa, uygulamanızı oluşturmaya ve çalıştırmaya hazırsınız:

   ![Yeni projeyi oluşturmaya hazır](media/vscpp-ready-to-build.png "Yeni projeyi oluşturmaya hazır")

## <a name="build-and-run-your-code-in-visual-studio"></a>Visual Studio'da kodunuzu oluşturun ve çalıştırın

1. Projenizi oluşturmak için **Yapı** menüsünden **Çözüm Oluştur'u** seçin. **Çıktı** penceresi yapı işleminin sonuçlarını gösterir.

   ![Projeyi derleme](media/vscpp-build-solution.gif "Projeyi derleme")

1. Kodu çalıştırmak için menü çubuğunda **Hata**Ayıklama'yı seçin, **hata ayıklama dan başlat.**

   ![Projeyi başlatın](media/vscpp-start-without-debugging.gif "Projeyi başlatın")

   Bir konsol penceresi açılır ve ardından uygulamanızı çalıştırır. Visual Studio'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır ve ardından "Devam etmek için herhangi bir tuşa basın. . ." çıktıyı görme şansı vermek için.

Tebrikler! İlk "Merhaba, dünya!" Visual Studio konsol uygulaması! Konsol penceresini kapatmak ve Visual Studio'ya dönmek için bir tuşa basın.

[Bir sorunla karşılaştım.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Kodunuzu komut penceresinde çalıştırma

Normalde konsol uygulamalarını Visual Studio'da değil komut istemiyle çalıştırın. Uygulamanız Visual Studio tarafından üretilirse, uygulamayı herhangi bir komut penceresinden çalıştırabilirsiniz. Yeni uygulamanızı komut istemi penceresinde şu şekilde bulabilir ve çalıştırabilirsiniz.

1. **Solution Explorer'da**HelloWorld çözümünü (HelloWorld projesi değil) seçin ve bağlam menüsünü açmak için sağ tıklayın. HelloWorld çözüm klasöründe dosya **gezgini** penceresini açmak için Dosya **Gezgini'nde Klasörü Aç'ı** seçin.

1. Dosya **Gezgini** penceresinde Hata Ayıklama klasörünü açın. Bu klasör, uygulamanız, *HelloWorld.exe*ve diğer hata ayıklama dosyaları bir çift içerir. **Shift** tuşunu basılı tutun ve bağlam menüsünü açmak için *HelloWorld.exe'ye* sağ tıklayın. Uygulamanızın panosuna giden yolu kopyalamak için **yol olarak Kopyala'yı** seçin.

1. Komut istemi penceresi açmak için **Çalıştır** iletişim kutusunu açmak için **Windows+R** tuşuna basın. **Açık** metin kutusuna *cmd.exe* girin, ardından komut istemi penceresini çalıştırmak için **Tamam'ı** seçin.

1. Komut istemi penceresinde, uygulamanızın yolunu komut istemine yapıştırmak için sağ tıklatın. Uygulamanızı çalıştırmak için Enter tuşuna basın.

   ![Uygulamayı komut isteminde çalıştırın](media/vscpp-run-in-cmd.gif "Uygulamayı komut isteminde çalıştırın")

Tebrikler, Visual Studio'da bir konsol uygulaması oluşturup çalıştırın!

[Bir sorunla karşılaştım.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Sonraki Adımlar

Bu basit uygulamayı oluşturup çalıştırdıktan sonra daha karmaşık projelere hazırsınız. Daha fazla bilgi için [C++ Masaüstü Geliştirme için Visual Studio IDE'yi kullanma bölümüne](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)bakın. Visual Studio'da Microsoft C++ özelliklerini inceleyen daha ayrıntılı gözden geçirme ler vardır.

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

İlk C++ projenizi oluştururken sık karşılaşılan sorunların çözümleri için buraya gelin.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Visual Studio'da kodunuzu oluşturun ve çalıştırın: sorunlar

Kaynak kod düzenleyicisinde herhangi bir şeyin altında kırmızı dalgalı hareketler görünüyorsa, yapıda hatalar veya uyarılar olabilir. Kodunuzu yazım, noktalama ve büyük harf örnekle eşleşip eşleşmediğini denetleyin.

[Geri Git.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Kodunuzu komut penceresinde çalıştırın: sorunlar

Dosya Gezgini'nde gösterilen yol * \\HelloWorld\\HelloWorld'de*sona eriyorsa, HelloWorld *çözümü*yerine HelloWorld *projesini* açtınız. Uygulamanızı içermeyen bir Hata Ayıklama klasörü kafanızı karıştırır. Yoldaki ilk *HelloWorld* olan çözüm klasörüne ulaşmak için Dosya Gezgini'nde bir düzeye gidin. Bu klasör de bir Hata Ayıklama klasörü içerir ve uygulamanızı orada bulabilirsiniz.

Ayrıca, uygulamanızı çalıştırmak için komut satırındaki çözüm Hata Ayıklama klasörüne de gidebilirsiniz. Uygulamanız, uygulamaya giden yolu belirtmeden diğer dizinlerden çalışmaz. Ancak, uygulamanızı başka bir dizine kopyalayabilir ve buradan çalıştırabilirsiniz. Ayrıca, PATH ortamı değişkeniniz tarafından belirtilen bir dizine kopyalayıp her yerden çalıştırmak da mümkündür.

Kısayol menüsünde **Kopyala'yı yol olarak** görmüyorsanız, menüyü kapatın ve yeniden açarken **Shift** tuşunu basılı tutun. Bu komut sadece kolaylık sağlamak içindir. Ayrıca Dosya Gezgini arama çubuğundan klasöre giden yolu kopyalayabilir ve **Çalıştır** iletişim kutusuna yapıştırabilir ve sonunda yürütülebilir olanınızın adını girebilirsiniz. Sadece biraz daha fazla yazma, ama aynı sonucu vardır.

[Geri Git.](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

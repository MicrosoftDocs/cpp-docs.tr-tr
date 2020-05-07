---
title: C++ konsol uygulama projesi derleyip çalıştırma
description: Visual C++ Merhaba Dünya konsol uygulaması oluşturun ve çalıştırın
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

Bir C++ konsol uygulaması projesi oluşturdunuz ve kodunuzu girdiniz. Artık Visual Studio içinde derleyip çalıştırabilirsiniz. Ardından, komut satırından tek başına bir uygulama olarak çalıştırın.

## <a name="prerequisites"></a>Ön koşullar

- Visual Studio 'Yu, C++ iş yükünün bilgisayarınızda yüklü ve çalışır şekilde masaüstü geliştirme ile birlikte çalıştırın. Henüz yüklenmemişse, [Visual Studio 'Da C++ desteğini yükleme](vscpp-step-0-installation.md)bölümündeki adımları uygulayın.

- "Hello, World!" oluşturun projeyi ve kaynak kodunu girin. Henüz bu adımı yapmadıysanız, [C++ konsol uygulama projesi oluşturma](vscpp-step-1-create.md)' daki adımları izleyin.

Visual Studio şuna benziyorsa, uygulamanızı oluşturmaya ve çalıştırmaya hazırsınız:

   ![Yeni projeyi oluşturmaya hazırlanıyor](media/vscpp-ready-to-build.png "Yeni projeyi oluşturmaya hazırlanıyor")

## <a name="build-and-run-your-code-in-visual-studio"></a>Visual Studio 'da kodunuzu derleyin ve çalıştırın

1. Projenizi derlemek için **derleme** menüsünden **çözüm oluştur** ' u seçin. **Çıkış** penceresi, derleme işleminin sonuçlarını gösterir.

   ![Projeyi derleme](media/vscpp-build-solution.gif "Projeyi derleme")

1. Kodu çalıştırmak için, menü çubuğunda **Hata Ayıkla**, **hata ayıklama olmadan Başlat**' ı seçin.

   ![Projeyi Başlat](media/vscpp-start-without-debugging.gif "Projeyi Başlat")

   Konsol penceresi açılır ve uygulamanızı çalıştırır. Visual Studio 'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır ve ardından devam etmek için herhangi bir tuşa basın. . ." çıktıyı görmeniz için bir şans sağlamak üzere.

Tebrikler! İlk "Hello, World!" dosyanızı oluşturdunuz Visual Studio 'da konsol uygulaması! Konsol penceresini kapatmak ve Visual Studio 'ya dönmek için bir tuşa basın.

[Bir sorunla karşılaştık.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Kodunuzu bir komut penceresinde çalıştırma

Normalde Konsol uygulamalarını, Visual Studio 'da değil, komut isteminde çalıştırırsınız. Uygulamanız Visual Studio tarafından derlendikten sonra herhangi bir komut penceresinden çalıştırabilirsiniz. Yeni uygulamanızı bir komut istemi penceresinde bulmak ve çalıştırmak için aşağıdaki adımları uygulayın.

1. **Çözüm Gezgini**, HelloWorld çözümünü seçin (HelloWorld projesini değil) ve sağ tıklayarak bağlam menüsünü açın. **Dosya Gezgini 'Nde klasörü aç '** ı seçerek HelloWorld çözüm klasöründeki bir **Dosya Gezgini** penceresini açın.

1. **Dosya Gezgini** penceresinde hata ayıklama klasörünü açın. Bu klasör, uygulamanızı, *HelloWorld. exe*' yi ve diğer birkaç hata ayıklama dosyasını içerir. **Shift** tuşunu basılı tutarak, bağlam menüsünü açmak için *HelloWorld. exe* ' ye sağ tıklayın. Uygulamanızın yolunu panoya kopyalamak için **yolu olarak Kopyala** ' yı seçin.

1. Bir komut istemi penceresi açmak için **Windows + R** tuşlarına basarak **Çalıştır** iletişim kutusunu açın. **Aç** metin kutusuna *cmd. exe* yazın ve ardından bir komut Istemi penceresi çalıştırmak için **Tamam** ' ı seçin.

1. Komut istemi penceresinde, uygulamanızın yolunu komut istemine yapıştırmak için sağ tıklayın. Uygulamanızı çalıştırmak için ENTER tuşuna basın.

   ![Uygulamayı komut isteminden çalıştırma](media/vscpp-run-in-cmd.gif "Uygulamayı komut isteminden çalıştırma")

Tebrikler, Visual Studio 'da bir konsol uygulaması oluşturup çalıştırdık!

[Bir sorunla karşılaştık.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Sonraki Adımlar

Bu basit uygulamayı oluşturup çalıştırdığınızda, daha karmaşık projeler için hazır olursunuz. Daha fazla bilgi için bkz. [C++ masaüstü geliştirme Için Visual STUDIO IDE 'Yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md). Visual Studio 'da Microsoft C++ yeteneklerini keşfetmenin daha ayrıntılı talimatları vardır.

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

İlk C++ projenizi oluştururken sık karşılaşılan sorunların çözümleri için buraya gelin.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Visual Studio 'da kodunuzu derleyin ve çalıştırın: sorunlar

Kırmızı dalgalı çizgiler kaynak kodu düzenleyicisinde herhangi bir şey görünürse, derlemede hata veya uyarı olabilir. Kodunuzun yazım, noktalama ve büyük harfli örnekle eşleşip eşleşmediğini denetleyin.

[Geri Git.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Kodunuzu bir komut penceresinde çalıştırın: sorunlar

Dosya Gezgini 'nde gösterilen yol * \\HelloWorld\\HelloWorld*içinde biterse, HelloWorld *çözümü*yerine HelloWorld *projesini* açtınız. Uygulamanızı içermeyen bir hata ayıklama klasörü tarafından karıştırılırsınız. Dosya Gezgini 'nde, yoldaki ilk *HelloWorld* olan çözüm klasörüne ulaşmak için bir düzey yukarı gidin. Bu klasör ayrıca bir hata ayıklama klasörü içerir ve uygulamanızı orada bulabilirsiniz.

Uygulamanızı çalıştırmak için komut satırındaki Çözüm hata ayıklama klasörüne de gidebilirsiniz. Uygulamanız, uygulamanın yolunu belirtmeden diğer dizinlerden çalışmaz. Ancak, uygulamanızı başka bir dizine kopyalayabilir ve oradan çalıştırabilirsiniz. Bunu, PATH ortam değişkeniniz tarafından belirtilen bir dizine kopyalamak ve sonra herhangi bir yerden çalıştırmak mümkündür.

Kısayol menüsünde **farklı Kopyala yolunu** görmüyorsanız, menüyü kapatın ve yeniden açtığınızda **SHIFT** tuşunu basılı tutun. Bu komut yalnızca kolaylık sağlamak için kullanılır. Ayrıca dosyanın yolunu dosya Gezgini arama çubuğundan kopyalayabilir ve **Çalıştır** iletişim kutusuna yapıştırabilir ve sonra da son olarak yürütülebilir dosyanızın adını girebilirsiniz. Bu çok az bir yazma, ancak aynı sonucu elde etti.

[Geri Git.](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

---
title: Derleme ve C++ konsol uygulama projesi çalıştırma
description: Visual c++'ta bir Hello World konsol uygulaması derleyebilir ve
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: 59813a553a9034503d8bf432400db31e6e3d9478
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813556"
---
# <a name="build-and-run-a-c-console-app-project"></a>Derleme ve C++ konsol uygulama projesi çalıştırma

Bir C++ konsol uygulama projesi oluşturmuş ve kodunuzu girilen, yapı ve Visual Studio içinden çalıştırın ve sonra tek başına bir uygulama olarak komut satırından çalıştırabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio ile masaüstü geliştirme, yüklü ve bilgisayarınızda çalışan C++ iş yükünde sahip. Henüz yüklü değilse, adımları [Visual Studio'da C++ yükleme desteği](vscpp-step-0-installation.md).

- Bir "Hello, World!" oluşturma Proje ve kaynak kodu girin. Bunu henüz yapmadıysanız adımları [C++ konsol uygulama projesi oluşturma](vscpp-step-1-create.md).

Visual Studio gibi görünüyorsa, oluşturmak ve uygulamanızı çalıştırmak hazır:

   ![Yeni Projeyi derlemek hazır](media/vscpp-ready-to-build.png "yeni projeyi derlemek hazır")

## <a name="build-and-run-your-code-in-visual-studio"></a>Derleme ve kodunuzu Visual Studio'da çalıştırma

1. Projenizi tercih **Çözümü Derle** gelen **derleme** menüsü. **Çıkış** penceresi yapı işleminin sonuçlarını gösterir.

   ![Proje derleme](media/vscpp-build-solution.gif "projeyi oluşturun")

1. Menü çubuğunda kodu çalıştırmak için tercih **hata ayıklama**, **ayıklamadan Başlat**.

   ![Proje başlangıç](media/vscpp-start-without-debugging.gif "projeyi Başlat")

   Bir konsol penceresi açar ve ardından uygulamanızı çalıştırır. Visual Studio'da konsol uygulaması başlattığınızda, kodunuz çalışır ve ardından baskı siparişi "devam etmek için herhangi bir tuşa basın. biçimindeki telefon numarasıdır. ." Çıktıyı görmek için bir fırsat vermek için.

Tebrikler! İlk oluşturduğunuz "Hello, world!" Visual Studio'da konsol uygulaması! Konsol penceresini kapatın ve Visual Studio'ya dönmek için bir tuşa basın.

[Bir sorunla karşılaşırsanız çalıştırdım.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Bir komut penceresinde kodunuzu çalıştırın

Normalde, konsol uygulamaları Visual Studio'da değil, komut isteminde çalıştırın. Visual Studio tarafından uygulamanızı oluşturulduktan sonra herhangi bir komut penceresinden çalıştırabilirsiniz. İşte nasıl bulacağınızı ve yeni uygulamanızı bir komut istemi penceresinde çalıştırın.

1. İçinde **Çözüm Gezgini**HelloWorld çözümü seçin ve bağlam menüsünü açmak için sağ tıklayın. Seçin **klasörü dosya Gezgini'nde Aç** açmak için bir **dosya Gezgini** HelloWorld Çözüm klasörü'ndeki penceresi.

1. İçinde **dosya Gezgini** penceresi, hata ayıklama klasörü açın. Bu, uygulamanızı ve HelloWorld.exe birkaç diğer hata ayıklama dosyalarını içerir. HelloWorld.exe seçin, bağlam menüsünü açmak için sağ tıklayın ve Shift tuşunu basılı tutun. Seçin **kopya yolu olarak** yolu uygulamanıza panoya kopyalamak için.

1. Bir komut istemi penceresi açmak için açmak için Windows-R tuşuna basın **çalıştırma** iletişim. Girin *cmd.exe* içinde **açık** metin seçin **Tamam** bir komut istemi penceresi çalıştırılacak.

1. Komut İstemi penceresinde, komut istemine yolu uygulamanıza yapıştırın için sağ tıklayın. Uygulamanızı çalıştırmak için Enter tuşuna basın.

   ![Uygulamayı komut isteminde çalıştırmak](media/vscpp-run-in-cmd.gif "uygulamayı komut isteminde çalıştırın.")

Tebrikler, oluşturulan ve Visual Studio'da konsol uygulaması çalıştırın!

[Bir sorunla karşılaşırsanız çalıştırdım.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Sonraki Adımlar

Yerleşik ve bu basit uygulama çalıştırma sonra daha karmaşık projeler için hazır olursunuz. Bkz: [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) Visual c++ in Visual Studio özelliklerini keşfedin izlenecek ayrıntılı için.

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

Burada, ilk C++ projenizi oluşturduğunuzda çözümleri için yaygın olarak karşılaşılan sorunlarını gelir.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Derleme ve kodunuzu Visual Studio sorunları çalıştırma

Kırmızı dalgalı çizgiler, kaynak kod düzenleyicisinde herhangi bir şey altında görünürse, yapı hataları ve Uyarıları olabilir. Kodunuzun çalışması yazım ve noktalama işaretleri örnekte eşleşip eşleşmediğini denetleyin.

[Geri Git.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Kodunuzu bir komut penceresinde sorunları çalıştırın.

Uygulamanızı çalıştırmak için komut satırına çözüm hata ayıklama klasöre gidebilirsiniz. Uygulama yolu belirtmeden diğer dizinlerden uygulamanızı çalıştıramazsınız. Ancak, uygulamanız başka bir dizine kopyalayın ve oradan çalıştırın.

Görmüyorsanız **kopya yolu olarak** kısayol menüsünde menüsünü bırakma ve yeniden açın SHIFT tuşunu basılı tutarak. Bu işlem yalnızca kolaylık sağlamaya yöneliktir. Ayrıca, yol dosya Gezgini arama çubuğunda klasöre kopyalayın ve yapıştırın **çalıştırma** iletişim kutusunda ve ardından son yürütülebilir dosyanızın adını girin. Biraz daha fazla yazarak olduğu, ancak aynı sonucu verir.

[Geri Git.](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

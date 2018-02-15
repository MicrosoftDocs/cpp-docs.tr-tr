---
title: "C++ konsol uygulaması projesini derlemeyi ve çalıştırmayı | Microsoft Docs"
description: "Visual C++ için Visual Studio desteğini yükleme"
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: get-started-article
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2bbc2db5a86d44d2beabe32e265e91ddb0c90787
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="build-and-run-a-c-console-app-project"></a>Derleme ve C++ konsol uygulama projesi çalıştırma

C++ konsol uygulama projesi oluşturduğunuzda ve kodunuzu girilen yapı ve Visual Studio çalıştırın ve ardından bu tek başına bir uygulama olarak komut satırından çalıştırın.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio masaüstü geliştirme ile yüklenmiş ve bilgisayarınızda çalışan C++ iş yükü var. Henüz yüklü değilse, adımları [Visual Studio yükleme C++ Destek](../build/vscpp-step-0-installation.md).

- Bir "Hello, World!" oluşturun Proje ve kaynak kodu girin. Bunu henüz yapmadıysanız adımları [C++ konsol uygulama projesi oluşturma](../build/vscpp-step-1-create.md).

Visual Studio gibi görünüyorsa, yapı ve uygulamanızı çalıştırmak hazırsınız:

   ![Yeni proje oluşturmak için hazır](../build/media/vscpp-ready-to-build.png "yeni proje oluşturmak için hazır")

## <a name="build-and-run-your-code-in-visual-studio"></a>Derleme ve Visual Studio'da kodunuzu çalıştırma

1. Projenizi derleme için tercih **Çözümü Derle** gelen **yapı** menüsü. **Çıkış** penceresi derleme işleminin sonuçlarını gösterir.

   ![Projeyi derlemek](../build/media/vscpp-build-solution.gif "projeyi oluşturun")

1. Menü çubuğunda kodu çalıştırmak için tercih **hata ayıklama**, **Başlat hata ayıklama olmadan**.

   ![Proje başlangıç](../build/media/vscpp-start-without-debugging.gif "projeyi başlatın")

    Bir konsol penceresi açar ve uygulamanızı çalışır. Visual Studio'da bir konsol uygulaması başlattığınızda, kodunuzu çalıştırır, sonra da baskı siparişi "devam etmek için herhangi bir tuşa basın. biçimindeki telefon numarasıdır. ." çıkışı görmek şansı vermek için.

Tebrikler! İlk oluşturduğunuz "Hello, world!" Visual Studio'da konsol uygulaması! Konsol penceresini kapatın ve Visual Studio'ya dönmek için bir tuşa basın.

[I bir sorunla karşılaştık.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>Bir komut penceresinde kodunuzu çalıştırmak

Normalde, komut isteminde, Visual Studio içinde değil konsol uygulamaları çalıştırın. Visual Studio tarafından uygulamanızı oluşturulduktan sonra bir komut penceresinde çalıştırabilirsiniz. İşte nasıl bulacağınızı ve bir komut istemi penceresinde yeni uygulamanızı çalıştırın.

1. İçinde **Çözüm Gezgini**, HelloWorld çözüm seçip bağlam menüsünü açmak için sağ tıklatın. Seçin **klasörünü dosya Gezgini'nde Aç** açmak için bir **dosya Gezgini** HelloWorld Çözüm klasörü penceresinde.

1. İçinde **dosya Gezgini** penceresi, hata ayıklama klasörünü açın. Bu, uygulamanızın, HelloWorld.exe ve birkaç diğer hata ayıklama dosyalarını içerir. HelloWorld.exe seçip Shift tuşunu basılı tutun ve bağlam menüsünü açmak için sağ tıklatın. Seçin **kopya yolu olarak** yolu uygulamanıza panoya kopyalamak için.

1. Bir komut istemi penceresi açmak için açmak için Windows-R tuşuna basın **çalıştırmak** iletişim. Girin *cmd.exe* içinde **açık** metin kutusuna, ardından **Tamam** bir komut istemi penceresi çalıştırmak için.

1. Komut İstemi penceresinde, komut istemine yolun uygulamanıza yapıştırın için sağ tıklatın. Uygulamanızı çalıştırmak için Enter tuşuna basın.

   ![Uygulamayı komut isteminde çalıştırmak](../build/media/vscpp-run-in-cmd.gif "uygulamayı komut isteminde çalıştırın")

Tebrikler, yerleşik ve Visual Studio konsol uygulamasını çalıştırın.

[I bir sorunla karşılaştık.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>Sonraki Adımlar

Yerleşik ve bu basit uygulama çalıştırma sonra daha karmaşık projeler için hazırsınız. Bkz: [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) Visual Studio'da Visual C++ özelliklerini keşfedin izlenecek ayrıntılı için.

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

Burada ilk C++ projenizi oluşturduğunuzda çözümleri için genel sorunlar gelir.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Derleme ve Visual Studio sorunlarını kodunuzu çalıştırma

Kırmızı dalgalı çizgiler kaynak kod düzenleyicisinde herhangi bir şey altında görünmüyorsa, derleme hataları ve Uyarıları olabilir. Kodunuzu yazımı, noktalama ve servis talebi örnekte eşleşip eşleşmediğini denetleyin.

[Geri Git.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>Kodunuzu bir komut penceresinde sorunları çalıştırın.

Uygulamanızı çalıştırmak için komut satırında çözüm hata ayıklama klasöre gidebilirsiniz. Uygulama yolu belirtmeden diğer dizinlerden uygulamanızı çalıştırılamıyor. Ancak, uygulamanızın başka bir dizine kopyalayın ve oradan çalıştırın.

Görmüyorsanız, **kopya yolu olarak** kısayol menüsünün menüsünü kapatın ve yeniden açın Shift tuşunu basılı tutarak. Bu, yalnızca kolaylık sağlamaya yöneliktir. Ayrıca, yol dosya Gezgini arama çubuğunda klasöre kopyalayın ve yapıştırın **çalıştırmak** iletişim kutusunda ve sonunda, yürütülebilir dosyanın adını girin. Biraz daha fazla yazarak olduğu, ancak aynı sonucu verir.

[Geri Git.](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

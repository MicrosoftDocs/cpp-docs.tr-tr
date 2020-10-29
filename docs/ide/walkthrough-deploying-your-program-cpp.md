---
title: 'İzlenecek Yol: Programınızı Dağıtma (C++)'
ms.date: 05/14/2019
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
ms.openlocfilehash: 6c5d98687d6b5a49fb7b4b90aecf345a739c34a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924673"
---
# <a name="walkthrough-deploying-your-program-c"></a>İzlenecek Yol: Programınızı Dağıtma (C++)

Daha önceki ilgili talimatları tamamlayarak uygulamanızı oluşturduğunuza göre son adım, diğer kullanıcıların programı bilgisayarlarına yükleyebilmeleri için bir yükleyici oluşturmaktır. Yükleyici için, var olan çözümünüze yeni bir proje ekleyeceksiniz. Bu yeni projenin çıktısı, uygulamanızı başka bir bilgisayara yükleyecek bir setup.exe dosyasıdır.

İzlenecek yol, uygulamanızı dağıtmak için Windows Installer nasıl kullanacağınızı gösterir. Ayrıca, ClickOnce kullanarak bir uygulamayı dağıtabilirsiniz. Daha fazla bilgi için bkz. [Visual C++ uygulamalar Için ClickOnce dağıtımı](../windows/clickonce-deployment-for-visual-cpp-applications.md). Genel olarak dağıtım hakkında daha fazla bilgi için bkz. [uygulamaları, hizmetleri ve bileşenleri dağıtma](/visualstudio/deployment/deploying-applications-services-and-components).

## <a name="prerequisites"></a>Önkoşullar

- İzlenecek yol, C++ dilinin temellerini anladığınızı varsayar.

- Ayrıca [, C++ masaüstü geliştirme Için Visual STUDIO IDE 'Yi kullanma](using-the-visual-studio-ide-for-cpp-desktop-development.md)bölümünde listelenen daha önceki ilgili talimatları tamamlamış olduğunu varsaymaktadır.

- İzlenecek yol, Visual Studio 'nun Express sürümlerinde tamamlanamaz.

## <a name="install-the-visual-studio-setup-and-deployment-project-template"></a>Visual Studio Kurulum ve dağıtım projesi şablonunu yükleme

Bu bölümdeki adımlar, yüklediğiniz Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

<!-- markdownlint-disable MD034 -->

::: moniker range="msvc-160"

### <a name="to-install-the-setup-and-deployment-project-template-for-visual-studio-2019"></a>Visual Studio 2019 için kurulum ve dağıtım proje şablonunu yüklemek için

1. Daha önce yapmadıysanız, Microsoft Visual Studio Installer projeleri uzantısını indirin. Uzantı, Visual Studio geliştiricileri için ücretsizdir ve kurulum ve dağıtım projesi şablonlarının işlevlerini Visual Studio 'ya ekler. Internet 'e bağlı olduğunuzda, Visual Studio **'da uzantıları**  >  **Yönet uzantılar** ' ı seçin. **Uzantılar ve güncelleştirmeler** Iletişim kutusunda **çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer projelerini* yazın. **ENTER** tuşuna basın, **Microsoft Visual Studio \<version> Yükleyici projeleri** ' ni seçin ve **İndir** ' e tıklayın. Uzantıyı çalıştırıp yüklemeyi seçip Visual Studio 'Yu yeniden başlatın.

1. Visual Studio menü çubuğunda **Dosya** > **son projeler ve çözümler** ' i seçin ve ardından projenizi yeniden açmak için seçin.

1. **File**  >  **New**  >  **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin. Arama kutusuna "Kurulum" yazın ve sonuçlar listesinden **Kurulum projesi** ' ni seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılan listesinde **çözüme Ekle** ' yi seçin. Kurulum projesi oluşturmak için **Tamam** düğmesini seçin. Bir **Dosya Yardımcısı (ProjectName)** sekmesi, düzenleyici penceresinde açılır.

1. **Uygulama klasörü** düğümüne sağ tıklayın ve proje çıktısı **Ekle** ' yi seçerek > **Project Output** **Proje çıkış grubu Ekle** iletişim kutusunu açın.

1. İletişim kutusunda, **birincil çıkış** ' ı seçin ve **Tamam** ' a tıklayın. **Oyunun birincil çıkışı (etkin)** adlı yeni bir öğe görünür.

1. **Oyunun birincil çıkışını (etkin)** seçin, sağ tıklayın ve **oyunun birincil çıkış için kısayol oluştur (etkin)** öğesini seçin. **Oyunun birincil çıktısına (etkin) kısayol** adlı yeni bir öğe görünür.

1. Kısayol öğesini *oyun* olarak yeniden adlandırın, ardından öğeyi sürükleyip pencerenin sol tarafındaki **Programlar menü** düğümüne bırakın.

1. **Çözüm Gezgini** , **oyun yükleyici** projesini seçin ve Özellikler **View** > penceresini açmak için **Özellikler** penceresini görüntüle ' yi veya **F4** ' **Properties** i tıklayın.

1. Yükleyicide görünmesini istediğiniz ek ayrıntıları belirtin.  Örneğin, **üretici** için *contoso* , **ürün adı** için *oyun yükleyicisi* ve **SupportUrl** için *https \: //www.contoso.com* kullanın.

1. Menü çubuğunda Configuration Manager **Oluştur** ' u seçin  >  **Configuration Manager** . **Proje** tablosunda, **derleme** sütununun altında **oyun yükleyicisi** kutusunu işaretleyin. **Kapat** ’a tıklayın.

1. Menü çubuğunda, **Build** > oyun projesini ve oyun yükleyici projesini oluşturmak için derleme **çözümü** oluştur ' u seçin.

1. Çözüm klasöründe, oyun yükleyicisi projesinden oluşturulan setup.exe programını bulun ve oyun uygulamasını bilgisayarınıza yüklemek için çalıştırın. Uygulamayı ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve GameInstaller.msi) kopyalayabilirsiniz.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-install-the-setup-and-deployment-project-template-for-visual-studio-2017-and-earlier"></a>Visual Studio 2017 ve öncesi için kurulum ve dağıtım projesi şablonunu yüklemek için

1. Internet 'e bağlı olduğunuzda, Visual Studio 'da **Araçlar** > **Uzantılar ve güncelleştirmeler** ' i seçin.

1. **Uzantılar ve güncelleştirmeler** altında **çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer projelerini* yazın. **ENTER** tuşuna basın, **Microsoft Visual Studio \<version> Yükleyici projeleri** ' ni seçin ve **İndir** ' e tıklayın.

1. Uzantıyı yüklemeyi seçin ve ardından Visual Studio 'Yu yeniden başlatın.

1. Menü çubuğunda, **File** > **son projeler ve çözümler** dosya ' yı seçin ve ardından yeniden açmak için **oyun** çözümünü seçin.

### <a name="to-create-a-setup-project-and-install-your-program"></a>Bir kurulum projesi oluşturup programınızı yükleme

1. Etkin çözüm yapılandırmasını sürüm olarak değiştirin. Menü çubuğunda Configuration Manager **Oluştur** ' u seçin  >  **Configuration Manager** . **Configuration Manager** iletişim kutusunda, **etkin çözüm yapılandırması** açılan listesinde, **yayın** ' ı seçin. Yapılandırmayı kaydetmek için **Kapat** düğmesini seçin.

1. **File** > **New** > **Yeni proje** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun sol bölmesinde, **yüklü**  >  **diğer proje türleri** düğümlerini genişletin ve **Visual Studio yükleyicisi** ' yi seçin. Orta bölmede, **Kurulum projesi** ' ni seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. Bu örnek için *oyun yükleyici* ' yi girin. **Çözüm** açılan listesinde **çözüme Ekle** ' yi seçin. Kurulum projesi oluşturmak için **Tamam** düğmesini seçin. Bir **Dosya Yardımcısı (oyun yükleyici)** sekmesi düzenleyici penceresinde açılır.

1. **Uygulama klasörü** düğümüne sağ tıklayın ve proje çıktısı **Ekle** ' yi seçerek > **Project Output** **Proje çıkış grubu Ekle** iletişim kutusunu açın.

1. İletişim kutusunda, **birincil çıkış** ' ı seçin ve **Tamam** ' a tıklayın. **Oyunun birincil çıkışı (etkin)** adlı yeni bir öğe görünür.

1. **Oyunun birincil çıkışını (etkin)** seçin, sağ tıklayın ve **oyunun birincil çıkış için kısayol oluştur (etkin)** öğesini seçin. **Oyunun birincil çıktısına (etkin) kısayol** adlı yeni bir öğe görünür.

1. Kısayol öğesini *oyun* olarak yeniden adlandırın, ardından öğeyi sürükleyip pencerenin sol tarafındaki **Programlar menü** düğümüne bırakın.

1. **Çözüm Gezgini** , **oyun yükleyici** projesini seçin ve Özellikler **View** > penceresini açmak için **Özellikler** penceresini görüntüle ' yi veya **F4** ' **Properties** i tıklayın.

1. Yükleyicide görünmesini istediğiniz ek ayrıntıları belirtin.  Örneğin, **üretici** için *contoso* , **ürün adı** için *oyun yükleyicisi* ve **SupportUrl** için *https \: //www.contoso.com* kullanın.

1. Menü çubuğunda Configuration Manager **Oluştur** ' u seçin  >  **Configuration Manager** . **Proje** tablosunda, **derleme** sütununun altında **oyun yükleyicisi** kutusunu işaretleyin. **Kapat** ’a tıklayın.

1. Menü çubuğunda, **Build** > oyun projesini ve oyun yükleyici projesini oluşturmak için derleme **çözümü** oluştur ' u seçin.

1. Çözüm klasöründe, oyun yükleyicisi projesinden oluşturulan setup.exe programını bulun ve oyun uygulamasını bilgisayarınıza yüklemek için çalıştırın. Uygulamayı ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve GameInstaller.msi) kopyalayabilirsiniz.

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

**Previous:** [Izlenecek yol: proje hatalarını ayıklama (C++)](walkthrough-debugging-a-project-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
[Masaüstü uygulamaları dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md)<br/>

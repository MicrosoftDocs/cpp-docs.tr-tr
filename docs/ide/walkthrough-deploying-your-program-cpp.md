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
ms.openlocfilehash: eacbcef82f240589e71b59f80d8e19602ceda869
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365015"
---
# <a name="walkthrough-deploying-your-program-c"></a>İzlenecek Yol: Programınızı Dağıtma (C++)

Daha önceki ilgili izthroughleri tamamlayarak uygulamanızı oluşturduğunuza göre, son adım, diğer kullanıcıların programı bilgisayarlarına yükleyebilmeleri için bir yükleyici oluşturmaktır. Yükleyici için, varolan çözümünüze yeni bir proje eklersiniz. Bu yeni projenin çıktısı, uygulamanızı başka bir bilgisayara yükleyecek bir setup.exe dosyasıdır.

Gözden geçirme, uygulamanızı dağıtmak için Windows Installer'ın nasıl kullanılacağını gösterir. Bir uygulamayı dağıtmak için ClickOnce'yi de kullanabilirsiniz. Daha fazla bilgi için [Visual C++ Uygulamaları için ClickOnce Dağıtım'a](../windows/clickonce-deployment-for-visual-cpp-applications.md)bakın. Genel olarak dağıtım hakkında daha fazla bilgi için [bkz.](/visualstudio/deployment/deploying-applications-services-and-components)

## <a name="prerequisites"></a>Ön koşullar

- Bu gözden geçirme, C++ dilinin temellerini anladığınızı varsayar.

- Ayrıca, [C++ Masaüstü Geliştirme için Visual Studio IDE'yi kullanma'da](using-the-visual-studio-ide-for-cpp-desktop-development.md)listelenen önceki ilgili gözden geçirme leri tamamladığınızı varsayar.

- Walkthrough Visual Studio Express sürümlerinde tamamlanamaz.

## <a name="install-the-visual-studio-setup-and-deployment-project-template"></a>Visual Studio kurulum ve dağıtım proje şablonu yükleme

Bu bölümdeki adımlar Visual Studio'nun hangi sürümünü yüklediğinize bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

<!-- markdownlint-disable MD034 -->

::: moniker range="vs-2019"

### <a name="to-install-the-setup-and-deployment-project-template-for-visual-studio-2019"></a>Visual Studio 2019 için kurulum ve dağıtım proje şablonu yüklemek için

1. Henüz yapmadıysanız, Microsoft Visual Studio Installer Projects uzantısını indirin. Uzantı Visual Studio geliştiricileri için ücretsizdir ve Visual Studio'ya kurulum ve dağıtım proje şablonlarının işlevselliğini ekler. Visual Studio'da Internet'e bağlandığınızda Uzantıları**Yönet Uzantıları'nı** **seçin.** >  **Uzantılar ve Güncelleştirmeler** iletişim kutusunun altında **Çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer Projects* yazın. **Enter'a**Girin , **Yükleyici Projeleri> Microsoft Visual Studio \<sürümünü**seçin ve **İndir'i**tıklatın. Uzantıyı çalıştırmayı ve yüklemeyi seçin ve ardından Visual Studio'yu yeniden başlatın.

1. Visual Studio menü çubuğunda, **Son Projeler ve Çözümleri** **Dosyala'yı** > seçin ve ardından projenizi yeniden açmayı seçin.

1. Menü çubuğunda, **Yeni Proje Oluştur** iletişim kutusunu açmak için**Yeni** > **Proje** **Dosyası'nı** > seçin. Arama kutusuna "Kurulum" yazın ve sonuç listesinden **Kurulum Projesi'ni**seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılır listesinde **çözüme ekle'yi**seçin. Kurulum projesini oluşturmak için **Tamam** düğmesini seçin. Düzenleyici penceresinde **Dosya Yardımcısı (ProjectName)** sekmesi açılır.

1. **Uygulama Klasörü** düğümüne sağ tıklayın ve Proje Çıktı Grubu Ekle iletişim kutusunu açmak için **Proje Çıktısı** **Ekle'yi** > seçin. **Add Project Output Group**

1. İletişim kutusunda, Birincil **Çıktı'yı** seçin ve **Tamam'ı**tıklatın. Oyundan Birincil **Çıktı (Etkin)** adlı yeni bir öğe görüntülenir.

1. **Oyundan Birincil Çıktı öğesini seçin (Etkin)**, sağ tıklayın ve Oyundan Birincil Çıktı için **Kısayol Oluştur'u seçin (Etkin)**. Oyundan Birincil **Çıktıya Kısayol (Etkin)** adlı yeni bir öğe görüntülenir.

1. Kısayol öğesini *Oyuna*yeniden adlandırın, ardından öğeyi sürükleyin ve pencerenin sol tarafındaki **Kullanıcı Programları Menüsü** düğümüne bırakın.

1. **Çözüm Gezgini'nde,** **Oyun Yükleyici** projesini seçin ve Özellikler **Penceresini** **Görüntüle'yi** > seçin veya **Özellikler** penceresini açmak için **F4'e** basın.

1. Yükleyicide görünmesini istediğiniz ek ayrıntıları belirtin.  Örneğin, **Üretici**için *Contoso'* yu, **Ürün Adı**için Oyun *Yükleyicisini* ve **SupportUrl**için *https\://www.contoso.com'ı* kullanın.

1. Menü çubuğunda**Yapı Yapılandırma Yöneticisi'ni** **seçin.** >  **Proje** tablosunda, **Yapı** sütununaltında, **Oyun Yükleyicisi**kutusunu işaretleyin. **Kapat'ı**tıklatın.

1. Menü çubuğunda, Oyun projesini ve Oyun Yükleyici projesini oluşturmak için **Build** > **Solution'ı** seçin.

1. Çözüm klasöründe, Oyun Yükleyici projesinden oluşturulmuş setup.exe programını bulun ve ardından Oyun uygulamasını bilgisayarınıza yüklemek için çalıştırın. Uygulamayı ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve GameInstaller.msi) kopyalayabilirsiniz.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-install-the-setup-and-deployment-project-template-for-visual-studio-2017-and-earlier"></a>Visual Studio 2017 ve daha önceki kurulum ve dağıtım proje şablonu yüklemek için

1. Visual Studio'da Internet'e bağlandığınızda, **Araç** > **Uzantıları ve Güncelleştirmeleri'ni**seçin.

1. **Uzantılar ve Güncelleştirmeler** **altında, Çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer Projects* yazın. **Enter'a**Girin , **Yükleyici Projeleri> Microsoft Visual Studio \<sürümünü**seçin ve **İndir'i**tıklatın.

1. Uzantıyı yüklemeyi seçin ve Ardından Visual Studio'yu yeniden başlatın.

1. Menü çubuğunda, **Dosya** > **Son Projeler ve Çözümler'i**seçin ve yeniden açmak için **Oyun** çözümünün seçeneğini belirleyin.

### <a name="to-create-a-setup-project-and-install-your-program"></a>Bir kurulum projesi oluşturmak ve programınızı yüklemek için

1. Etkin çözüm yapılandırmasını Release olarak değiştirin. Menü çubuğunda**Yapı Yapılandırma Yöneticisi'ni** **seçin.** >  Configuration **Manager** iletişim kutusunda, **Etkin çözüm yapılandırma** açılır listesinde **Serbest Bırak'ı**seçin. Yapılandırmayı kaydetmek için **Kapat** düğmesini seçin.

1. Menü çubuğunda, **Yeni Proje** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun sol bölmesinde, **Yüklenilen** > **Diğer Proje Türleri** düğümlerini genişletin ve ardından Visual Studio **Installer'ı**seçin. Orta bölmede Kurulum **Projesi'ni**seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. Bu örnekiçin, *Oyun Yükleyici*girin. **Çözüm** açılır listesinde **çözüme ekle'yi**seçin. Kurulum projesini oluşturmak için **Tamam** düğmesini seçin. Düzenleyici penceresinde **Dosya Yardımcısı (Oyun Yükleyici)** sekmesi açılır.

1. **Uygulama Klasörü** düğümüne sağ tıklayın ve Proje Çıktı Grubu Ekle iletişim kutusunu açmak için **Proje Çıktısı** **Ekle'yi** > seçin. **Add Project Output Group**

1. İletişim kutusunda, Birincil **Çıktı'yı** seçin ve **Tamam'ı**tıklatın. Oyundan Birincil **Çıktı (Etkin)** adlı yeni bir öğe görüntülenir.

1. **Oyundan Birincil Çıktı öğesini seçin (Etkin)**, sağ tıklayın ve Oyundan Birincil Çıktı için **Kısayol Oluştur'u seçin (Etkin)**. Oyundan Birincil **Çıktıya Kısayol (Etkin)** adlı yeni bir öğe görüntülenir.

1. Kısayol öğesini *Oyuna*yeniden adlandırın, ardından öğeyi sürükleyin ve pencerenin sol tarafındaki **Kullanıcı Programları Menüsü** düğümüne bırakın.

1. **Çözüm Gezgini'nde,** **Oyun Yükleyici** projesini seçin ve Özellikler **Penceresini** **Görüntüle'yi** > seçin veya **Özellikler** penceresini açmak için **F4'e** basın.

1. Yükleyicide görünmesini istediğiniz ek ayrıntıları belirtin.  Örneğin, **Üretici**için *Contoso'* yu, **Ürün Adı**için Oyun *Yükleyicisini* ve **SupportUrl**için *https\://www.contoso.com'ı* kullanın.

1. Menü çubuğunda**Yapı Yapılandırma Yöneticisi'ni** **seçin.** >  **Proje** tablosunda, **Yapı** sütununaltında, **Oyun Yükleyicisi**kutusunu işaretleyin. **Kapat'ı**tıklatın.

1. Menü çubuğunda, Oyun projesini ve Oyun Yükleyici projesini oluşturmak için **Build** > **Solution'ı** seçin.

1. Çözüm klasöründe, Oyun Yükleyici projesinden oluşturulmuş setup.exe programını bulun ve ardından Oyun uygulamasını bilgisayarınıza yüklemek için çalıştırın. Uygulamayı ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve GameInstaller.msi) kopyalayabilirsiniz.

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [Walkthrough: Bir Proje hata ayıklama (C++)](walkthrough-debugging-a-project-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[Projeler ve yapı sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
[Masaüstü Uygulamalarını Dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md)<br/>

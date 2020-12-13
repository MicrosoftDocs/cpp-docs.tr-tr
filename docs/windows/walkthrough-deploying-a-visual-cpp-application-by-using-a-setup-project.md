---
description: 'Daha fazla bilgi edinin: Izlenecek yol: kurulum projesi kullanarak Visual C++ uygulaması dağıtma'
title: Kurulum projesi kullanarak Visual C++ uygulaması dağıtma
ms.date: 04/25/2019
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
ms.openlocfilehash: 3815ce7a489440d6ae7db6bc73a1c17d02d46ae3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135999"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>İzlenecek Yol: Kurulum Projesi Kullanarak Visual C++ Uygulamasını Dağıtma

Bir Visual C++ uygulamasını dağıtmak için Kurulum projesinin nasıl kullanılacağını açıklar.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Visual Studio yüklü bir bilgisayar.

- Visual C++ kitaplıkları olmayan ek bir bilgisayar.

## <a name="create-the-setup-project"></a>Kurulum projesi oluşturma

Kurulum projesi oluşturma yönergeleri, yüklediğiniz Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="=msvc-160"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de proje oluşturmak için

1.  >  > **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin.

   ![MFC Uygulama Projesi](media/vs2019-mfc-app-new-project.png "Yeni MFC uygulaması")

1. İletişim kutusunun üst kısmındaki `MFC` Arama kutusuna yazın ve ardından sonuçlar listesinden **MFC uygulaması** ' nı seçin. Bunu görmüyorsanız, Windows Başlat menüsünden Visual Studio Yükleyicisi programını başlatmanız ve **C++ masaüstü geliştirme iş yükü** kutucuğuna tıklamanız gerekir. **Ayrı bileşenler** altında MFC bileşeninin işaretli olduğundan emin olun.

1. Sonraki sayfada, proje için bir ad girin ve isterseniz proje konumunu belirtin.

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin. **MFC Uygulama Sihirbazı** göründüğünde tüm varsayılanları kabul edin.

1. Etkin çözüm yapılandırmasını **Sürüm** olarak değiştirin. **Build** menüsünde, **Yapılandırma Yöneticisi**' ni seçin. **Configuration Manager** iletişim kutusunda, **etkin çözüm yapılandırması** açılan kutusundan **Yayınla** ' yı seçin. **Kapat**’a tıklayın.

1.  +  + Uygulamayı derlemek için CTRL SHIFT **B** tuşlarına basın. Ya da **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulamanın oluşturulması, Kurulum projesinin bu MFC Uygulama projesinin çıkışını kullanmasını sağlar.

1. Daha önce yapmadıysanız, Microsoft Visual Studio Installer projeleri uzantısını indirin. Uzantı, Visual Studio geliştiricileri için ücretsizdir ve kurulum ve dağıtım projesi şablonlarının işlevlerini Visual Studio 'ya ekler. Internet 'e bağlı olduğunuzda, Visual Studio **'da uzantıları**  >  **Yönet uzantılar**' ı seçin. **Uzantılar ve güncelleştirmeler** Iletişim kutusunda **çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer projelerini* yazın. **ENTER** tuşuna basın, **Microsoft Visual Studio \<version> Yükleyici projeleri**' ni seçin ve **İndir**' e tıklayın. Uzantıyı çalıştırıp yüklemeyi seçip Visual Studio 'Yu yeniden başlatın.

   ![Visual Studio Kurulum projesi](media/vs2019-extension-dialog-installer-project.png "İstemci projesini adlandırın")

1. Visual Studio menü çubuğunda **Dosya** > **son projeler ve çözümler**' i seçin ve ardından projenizi yeniden açmak için seçin.

1.   >    >  **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin. Arama kutusuna "Kurulum" yazın ve sonuçlar listesinden **Kurulum projesi**' ni seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılan listesinde **çözüme Ekle**' yi seçin. Kurulum projesi oluşturmak için **Tamam** düğmesini seçin. Bir **Dosya Yardımcısı (ProjectName)** sekmesi, düzenleyici penceresinde açılır.

::: moniker-end

::: moniker range="=msvc-150"

### <a name="to-create-the-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de proje oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde, **Yeni**' nin üzerine gelin ve ardından **Proje**' ye tıklayın.

1. Yeni bir Visual Studio çözümü oluşturmak için **MFC Uygulama Sihirbazı 'nı** kullanın. Sihirbazı bulmak için **Yeni proje** iletişim kutusundan **Visual C++** düğümünü genişletin, **MFC**'yi seçin, **MFC uygulaması**' nı seçin, proje için bir ad girin ve ardından **Tamam**' a tıklayın. **Finish (Son)** düğmesine tıklayın.

   > [!NOTE]
   > **MFC Uygulama** türü eksikse, **Yeni proje** iletişim kutusunun sol bölmesindeki **Visual Studio yükleyicisi aç** ' ı seçin. **X86 ve x64 için VISUAL C++ MFC** adlı **isteğe bağlı** bileşenler bölümünde **C++ ile masaüstü geliştirme** altında bulunan seçeneğini yükler.

1. Etkin çözüm yapılandırmasını **Sürüm** olarak değiştirin. **Build** menüsünde, **Yapılandırma Yöneticisi**' ni seçin. **Configuration Manager** iletişim kutusunda, **etkin çözüm yapılandırması** açılan kutusundan **Yayınla** ' yı seçin. **Kapat**’a tıklayın.

1.  +  + Uygulamayı derlemek için CTRL SHIFT **B** tuşlarına basın. Ya da **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulamanın oluşturulması, Kurulum projesinin bu MFC Uygulama projesinin çıkışını kullanmasını sağlar.

1. Daha önce yapmadıysanız, Microsoft Visual Studio Installer projeleri uzantısını indirin. Uzantı, Visual Studio geliştiricileri için ücretsizdir ve kurulum ve dağıtım projesi şablonlarının işlevlerini Visual Studio 'ya ekler. Internet 'e bağlı olduğunuzda, Visual Studio 'da **Araçlar**  >  **Uzantılar ve güncelleştirmeler**' i seçin. **Uzantılar ve güncelleştirmeler** Iletişim kutusunda **çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer projelerini* yazın. **ENTER** tuşuna basın, **Microsoft Visual Studio \<version> Yükleyici projeleri**' ni seçin ve **İndir**' e tıklayın. Uzantıyı çalıştırıp yüklemeyi seçip Visual Studio 'Yu yeniden başlatın.

1. Menü çubuğunda **Dosya** > **son projeler ve çözümler**' i seçin ve ardından projenizi yeniden açmak için seçin.

1.   >    >  **Yeni proje** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin. Ardından iletişim kutusunun sol bölmesinde, **yüklü**  >  **diğer proje türleri** düğümlerini genişletin ve **Visual Studio yükleyicisi**' yi seçin. Orta bölmede, **Kurulum projesi**' ni seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılan listesinde **çözüme Ekle**' yi seçin. Kurulum projesi oluşturmak için **Tamam** düğmesini seçin. Bir **Dosya Yardımcısı (ProjectName)** sekmesi, düzenleyici penceresinde açılır.

::: moniker-end

::: moniker range="=msvc-140"

### <a name="to-create-the-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de proje oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde, **Yeni**' nin üzerine gelin ve ardından **Proje**' ye tıklayın.

1. Yeni bir Visual Studio çözümü oluşturmak için **MFC Uygulama Sihirbazı 'nı** kullanın. Sihirbazı bulmak için **Yeni proje** iletişim kutusundan **Visual C++** düğümünü genişletin, **MFC**'yi seçin, **MFC uygulaması**' nı seçin, proje için bir ad girin ve ardından **Tamam**' a tıklayın. **Finish (Son)** düğmesine tıklayın.

   > [!NOTE]
   > **MFC Uygulama** türü eksikse, Windows Başlat düğmesine tıklayın ve **Program Ekle Kaldır** yazın. Program sonuçlar listesinden açın ve ardından yüklü programlar listesinde Microsoft Visual Studio 2015 yüklemenizi bulun. Çift tıklayın, ardından **Değiştir** ' i seçin ve **Visual C++** altında **Microsoft Foundation sınıfları** bileşeni seçin.

1. Etkin çözüm yapılandırmasını **Sürüm** olarak değiştirin. **Build** menüsünden **Configuration Manager**' yi seçin. **Configuration Manager** iletişim kutusunda, **etkin çözüm yapılandırması** açılan kutusundan **Yayınla** ' yı seçin. **Kapat**’a tıklayın.

1.  +  + Uygulamayı derlemek için CTRL SHIFT **B** tuşlarına basın. Ya da **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulamanın oluşturulması, Kurulum projesinin bu MFC Uygulama projesinin çıkışını kullanmasını sağlar.

1. Daha önce yapmadıysanız, Microsoft Visual Studio Installer projeleri uzantısını indirin. Uzantı, Visual Studio geliştiricileri için ücretsizdir ve kurulum ve dağıtım projesi şablonlarının işlevlerini Visual Studio 'ya ekler. Internet 'e bağlı olduğunuzda, Visual Studio 'da **Araçlar**  >  **Uzantılar ve güncelleştirmeler**' i seçin. **Uzantılar ve güncelleştirmeler** Iletişim kutusunda **çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer projelerini* yazın. **ENTER** tuşuna basın, **Microsoft Visual Studio \<version> Yükleyici projeleri**' ni seçin ve **İndir**' e tıklayın. Uzantıyı çalıştırıp yüklemeyi seçip Visual Studio 'Yu yeniden başlatın.

1. Menü çubuğunda **Dosya** > **son projeler ve çözümler**' i seçin ve ardından projenizi yeniden açmak için seçin.

1.   >    >  **Yeni proje** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin. Ardından iletişim kutusunun sol bölmesinde, **yüklü**  >  **diğer proje türleri** düğümlerini genişletin ve **Visual Studio yükleyicisi**' yi seçin. Orta bölmede, **Kurulum projesi**' ni seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılan listesinde **çözüme Ekle**' yi seçin. Kurulum projesi oluşturmak için **Tamam** düğmesini seçin. Bir **Dosya Yardımcısı (ProjectName)** sekmesi, düzenleyici penceresinde açılır.

::: moniker-end

## <a name="add-items-to-the-project"></a>Projeye öğe ekleme

1. **Uygulama klasörü** düğümüne sağ tıklayın ve proje çıktısı **Ekle**' yi seçerek  >   **Proje çıkış grubu Ekle** iletişim kutusunu açın. İletişim kutusunda, **birincil çıkış** ' ı seçin ve **Tamam**' a tıklayın. **ProjectName (etkin) kaynağından birincil çıkış** adlı yeni bir öğe görünür.

1. **Uygulama klasörü** düğümüne sağ tıklayın ve   >  **Bileşen Seç** iletişim kutusunu açmak için **derleme** Ekle ' yi seçin. [Hangi dll 'lerin yeniden dağıtılacağını belirleyen](determining-which-dlls-to-redistribute.md)makalede açıklandığı gibi programın gerektirdiği gerekli dll 'leri seçin ve ekleyin.

1. **ProjectName (etkin) öğesinden öğe birincil çıkışını** seçin, sağ tıklayın ve **ProjectName (etkin) öğesinden birincil çıkış için kısayol oluştur**' u seçin. **ProjectName (etkin) kaynağından birincil çıkış Için kısayol** adlı yeni bir öğe görünür. Kısayol öğesini yeniden adlandırabilir, ardından öğeyi sürükleyip pencerenin sol tarafındaki **kullanıcıların programlar menü** düğümüne bırakabilirsiniz.

1. Menü çubuğunda Configuration Manager **Oluştur**' u seçin  >  . **Proje** tablosunda, **derleme** sütununun altında, dağıtım projesinin kutusunu işaretleyin. **Kapat**’a tıklayın.

1. Menü çubuğunda,   >  MFC projesini ve dağıtım projesini derlemek için derleme **çözümü** oluştur ' u seçin.

1. Çözüm klasöründe, dağıtım projesinden oluşturulan setup.exe programını bulun. Uygulamayı ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve. msi dosyasını) kopyalayabilirsiniz. Kurulum programını Visual C++ kitaplıkları olmayan ikinci bir bilgisayarda çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım örnekleri](deployment-examples.md)<br/>

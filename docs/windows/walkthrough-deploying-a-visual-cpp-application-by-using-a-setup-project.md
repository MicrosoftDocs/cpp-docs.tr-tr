---
title: Kurulum Projesi Kullanarak Visual C++ Uygulamasını Dağıtma
ms.date: 04/25/2019
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
ms.openlocfilehash: 8a1242140154c5a0123d71b83983fae20cab5d7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374353"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>İzlenecek Yol: Kurulum Projesi Kullanarak Visual C++ Uygulamasını Dağıtma

Visual C++ uygulamasını dağıtmak için kurulum projesinin nasıl kullanılacağını açıklar.

## <a name="prerequisites"></a>Ön koşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Visual Studio yüklü bir bilgisayar.

- Visual C++ kitaplıkları olmayan ek bir bilgisayar.

## <a name="create-the-setup-project"></a>Kurulum projesini oluşturma

Kurulum projesi oluşturma yönergeleri, Visual Studio'nun hangi sürümünü yüklediğinize bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="=vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Visual Studio 2019'da proje oluşturmak

1. Menü çubuğunda, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

   ![MFC App projesi](media/vs2019-mfc-app-new-project.png "Yeni MFC uygulaması")

1. İletişim kutusunun üst kısmında `MFC` arama kutusuna yazın ve ardından sonuç listesinden **MFC Uygulamasını** seçin. Görmüyorsanız, Visual Studio Installer programını Windows Başlat menüsünden başlatmanız ve **C++ Masaüstü Geliştirme iş yükü** döşemesini tıklatmanız gerekir. **Tek tek Bileşenler**altında, MFC bileşeninin denetlediğinden emin olun.

1. Sonraki sayfada, proje için bir ad girin ve istenirse proje konumunu belirtin.

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin. **MFC Uygulama Sihirbazı** göründüğünde, tüm varsayılanları kabul edin.

1. Etkin çözüm yapılandırmasını Release olarak **değiştirin.** **Yapı** menüsünden **Configuration Manger'ı**seçin. Configuration **Manager** iletişim kutusundan, Etkin **çözüm yapılandırma** açılır kutusundan **Serbest Bırak'ı** seçin. **Kapat'ı**tıklatın.

1. Uygulamayı oluşturmak için **Ctrl**+**Shift**+**B** tuşuna basın. Veya **Yapı** menüsünde **Çözüm Oluştur'u**tıklatın. Uygulamanın oluşturulması, kurulum projesinin bu MFC uygulama projesinin çıktısını kullanmasını sağlar.

1. Henüz yapmadıysanız, Microsoft Visual Studio Installer Projects uzantısını indirin. Uzantı Visual Studio geliştiricileri için ücretsizdir ve Visual Studio'ya kurulum ve dağıtım proje şablonlarının işlevselliğini ekler. Visual Studio'da Internet'e bağlandığınızda Uzantıları**Yönet Uzantıları'nı** **seçin.** >  **Uzantılar ve Güncelleştirmeler** iletişim kutusunun altında **Çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer Projects* yazın. **Enter**tuşuna basın, **Yükleyici Projeleri> Microsoft Visual Studio \<sürümünü**seçin ve **İndir'i**tıklatın. Uzantıyı çalıştırmayı ve yüklemeyi seçin ve ardından Visual Studio'yu yeniden başlatın.

   ![Visual Studio kurulum projesi](media/vs2019-extension-dialog-installer-project.png "İstemci projesini adlandırın")

1. Visual Studio menü çubuğunda, **Son Projeler ve Çözümleri** **Dosyala'yı** > seçin ve ardından projenizi yeniden açmayı seçin.

1. Menü çubuğunda, **Yeni Proje Oluştur** iletişim kutusunu açmak için**Yeni** > **Proje** **Dosyası'nı** > seçin. Arama kutusuna "Kurulum" yazın ve sonuç listesinden **Kurulum Projesi'ni**seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılır listesinde **çözüme ekle'yi**seçin. Kurulum projesini oluşturmak için **Tamam** düğmesini seçin. Düzenleyici penceresinde **Dosya Yardımcısı (ProjectName)** sekmesi açılır.

::: moniker-end

::: moniker range="=vs-2017"

### <a name="to-create-the-project-in-visual-studio-2017"></a>Visual Studio 2017'de proje oluşturmak

1. Yeni bir proje oluşturma. **Dosya** menüsünde **Yeni'yi**işaret edin ve ardından **Project'i**tıklatın.

1. Yeni bir Visual Studio çözümü oluşturmak için **MFC Uygulama Sihirbazı'nı** kullanın. **Sihirbazı** bulmak için, Yeni Proje iletişim kutusundan, **Visual C++** düğümünü genişletin, **MFC'yi**seçin, **MFC Uygulamasını**seçin, proje için bir ad girin ve sonra **Tamam'ı**tıklatın. **Son**'a tıklayın.

   > [!NOTE]
   > **MFC Uygulama** türü eksikse, **Yeni Proje** iletişim kutusunun sol bölmesinde Görsel **Stüdyo Yükleyicisini Aç'ı** seçin. **X86 ve x64 için Visual C++ MFC**adlı **İsteğe bağlı** bileşenler bölümünde **C++ ile Masaüstü geliştirme** altında bulunan seçeneği yükleyin.

1. Etkin çözüm yapılandırmasını Release olarak **değiştirin.** **Yapı** menüsünden **Configuration Manger'ı**seçin. Configuration **Manager** iletişim kutusundan, Etkin **çözüm yapılandırma** açılır kutusundan **Serbest Bırak'ı** seçin. **Kapat'ı**tıklatın.

1. Uygulamayı oluşturmak için **Ctrl**+**Shift**+**B** tuşuna basın. Veya **Yapı** menüsünde **Çözüm Oluştur'u**tıklatın. Uygulamanın oluşturulması, kurulum projesinin bu MFC uygulama projesinin çıktısını kullanmasını sağlar.

1. Henüz yapmadıysanız, Microsoft Visual Studio Installer Projects uzantısını indirin. Uzantı Visual Studio geliştiricileri için ücretsizdir ve Visual Studio'ya kurulum ve dağıtım proje şablonlarının işlevselliğini ekler. Visual Studio'da Internet'e bağlandığınızda, **Araç** > **Uzantıları ve Güncelleştirmeleri'ni**seçin. **Uzantılar ve Güncelleştirmeler** iletişim kutusunun altında **Çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer Projects* yazın. **Enter**tuşuna basın, **Yükleyici Projeleri> Microsoft Visual Studio \<sürümünü**seçin ve **İndir'i**tıklatın. Uzantıyı çalıştırmayı ve yüklemeyi seçin ve ardından Visual Studio'yu yeniden başlatın.

1. Menü çubuğunda, **Son Projeleri ve Çözümleri** **Dosyala'yı** > seçin ve ardından projenizi yeniden açmayı seçin.

1. Menü çubuğunda, **Yeni Proje** iletişim kutusunu açmak için**Yeni** > **Proje** **Dosyası'nı** > seçin. Ardından iletişim kutusunun sol bölmesinde, **Yüklenen** > **Diğer Proje Türleri** düğümlerini genişletin ve Visual Studio **Installer'ı**seçin. Orta bölmede Kurulum **Projesi'ni**seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılır listesinde **çözüme ekle'yi**seçin. Kurulum projesini oluşturmak için **Tamam** düğmesini seçin. Düzenleyici penceresinde **Dosya Yardımcısı (ProjectName)** sekmesi açılır.

::: moniker-end

::: moniker range="=vs-2015"

### <a name="to-create-the-project-in-visual-studio-2015"></a>Visual Studio 2015'te proje oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde **Yeni'yi**işaret edin ve ardından **Project'i**tıklatın.

1. Yeni bir Visual Studio çözümü oluşturmak için **MFC Uygulama Sihirbazı'nı** kullanın. **Sihirbazı** bulmak için, Yeni Proje iletişim kutusundan, **Visual C++** düğümünü genişletin, **MFC'yi**seçin, **MFC Uygulamasını**seçin, proje için bir ad girin ve sonra **Tamam'ı**tıklatın. **Son**'a tıklayın.

   > [!NOTE]
   > **MFC Uygulama** türü eksikse, Windows Başlat düğmesini tıklatın ve **Programları Kaldır'ı ekle**yazın. Programı sonuç listesinden açın ve microsoft Visual Studio 2015 yüklemenizi yüklü programlar listesinde bulun. Çift tıklatın, sonra **Değiştir'i** seçin ve **Visual C++** altında **Microsoft Hazırlık Sınıfları** bileşenini seçin.

1. Etkin çözüm yapılandırmasını Release olarak **değiştirin.** **Yapı** menüsünden **Configuration Manager'ı**seçin. Configuration **Manager** iletişim kutusundan, Etkin **çözüm yapılandırma** açılır kutusundan **Serbest Bırak'ı** seçin. **Kapat'ı**tıklatın.

1. Uygulamayı oluşturmak için **Ctrl**+**Shift**+**B** tuşuna basın. Veya **Yapı** menüsünde **Çözüm Oluştur'u**tıklatın. Uygulamanın oluşturulması, kurulum projesinin bu MFC uygulama projesinin çıktısını kullanmasını sağlar.

1. Henüz yapmadıysanız, Microsoft Visual Studio Installer Projects uzantısını indirin. Uzantı Visual Studio geliştiricileri için ücretsizdir ve Visual Studio'ya kurulum ve dağıtım proje şablonlarının işlevselliğini ekler. Visual Studio'da Internet'e bağlandığınızda, **Araç** > **Uzantıları ve Güncelleştirmeleri'ni**seçin. **Uzantılar ve Güncelleştirmeler** iletişim kutusunun altında **Çevrimiçi** sekmesini seçin ve arama kutusuna *Microsoft Visual Studio Installer Projects* yazın. **Enter**tuşuna basın, **Yükleyici Projeleri> Microsoft Visual Studio \<sürümünü**seçin ve **İndir'i**tıklatın. Uzantıyı çalıştırmayı ve yüklemeyi seçin ve ardından Visual Studio'yu yeniden başlatın.

1. Menü çubuğunda, **Son Projeleri ve Çözümleri** **Dosyala'yı** > seçin ve ardından projenizi yeniden açmayı seçin.

1. Menü çubuğunda, **Yeni Proje** iletişim kutusunu açmak için**Yeni** > **Proje** **Dosyası'nı** > seçin. Ardından iletişim kutusunun sol bölmesinde, **Yüklenen** > **Diğer Proje Türleri** düğümlerini genişletin ve Visual Studio **Installer'ı**seçin. Orta bölmede Kurulum **Projesi'ni**seçin.

1. **Ad** kutusuna kurulum projesi için bir ad girin. **Çözüm** açılır listesinde **çözüme ekle'yi**seçin. Kurulum projesini oluşturmak için **Tamam** düğmesini seçin. Düzenleyici penceresinde **Dosya Yardımcısı (ProjectName)** sekmesi açılır.

::: moniker-end

## <a name="add-items-to-the-project"></a>Projeye öğe ekleme

1. **Uygulama Klasörü** düğümüne sağ tıklayın ve Proje Çıktı Grubu Ekle iletişim kutusunu açmak için**Proje Çıktısı** **Ekle'yi** > seçin. **Add Project Output Group** İletişim kutusunda, Birincil **Çıktı'yı** seçin ve **Tamam'ı**tıklatın. **ProjectName'den (Etkin) Birincil Çıktı** adlı yeni bir öğe görüntülenir.

1. **Uygulama Klasörü** düğümüne sağ tıklayın ve **Bileşeni Seç** iletişim kutusunu açmak için**Derleme** **Ekle'yi** > seçin. [Hangi DL'lerin Yeniden Dağıtılmak Üzere](determining-which-dlls-to-redistribute.md)Olduğunu Belirleyen makalede açıklandığı gibi, programın gerektirdiği gerekli DL'leri seçin ve ekleyin.

1. **ProjectName (Active) öğesi Birincil Çıktı'yı**seçin, sağ tıklatın ve **ProjectName'den Birincil Çıktıya Kısayol Oluştur'u seçin (Etkin)**. **ProjectName'den (Etkin) Birincil Çıktıya Kısayol** adlı yeni bir öğe görüntülenir. Kısayol öğesini yeniden adlandırabilir, ardından öğeyi sürükleyip pencerenin sol tarafındaki **Kullanıcı Programları Menüsü** düğümüne bırakabilirsiniz.

1. Menü çubuğunda**Yapı Yapılandırma Yöneticisi'ni** **seçin.** >  **Proje** tablosunda, **Yapı** sütununaltında, dağıtım projesi için kutuyu işaretleyin. **Kapat'ı**tıklatın.

1. Menü çubuğunda, MFC projesini ve dağıtım projesini oluşturmak için **Yapı** > **Çözüm'üne** bakın.

1. Çözüm klasöründe, dağıtım projesinden oluşturulmuş setup.exe programını bulun. Uygulamayı ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve .msi dosyasını) kopyalayabilirsiniz. Kurulum programını Visual C++ kitaplıkları olmayan ikinci bir bilgisayarda çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>

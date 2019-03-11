---
title: Bir kurulum projesi kullanarak Visual C++ uygulamasını dağıtma
ms.date: 09/17/2018
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
ms.openlocfilehash: e2d83d45f1369e250b24708edd17f4004e030a17
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749132"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>İzlenecek yol: Bir kurulum projesi kullanarak Visual C++ uygulamasını dağıtma

Visual C++ uygulaması dağıtmak için bir kurulum projesi kullanmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Visual Studio'nun yüklü olduğu bir bilgisayar.

- Visual C++ kitaplıkları sahip olmayan başka bir bilgisayar.

### <a name="to-deploy-an-application-by-using-a-setup-project"></a>Bir kurulum projesi kullanarak bir uygulamayı dağıtmak için

1. Yeni bir proje oluşturun. Üzerinde **dosya** menüsünde **yeni**ve ardından **proje**.

1. Kullanım **MFC ApplicationWizard** yeni bir Visual Studio çözümü oluşturmak için. Sihirbaz bulmalarına için **yeni proje** iletişim kutusunda **Visual C++** düğümünü **MFC**seçin **MFC uygulaması**, girin bir Projeyi adlandırın ve ardından **Tamam**. **Son**'a tıklayın.

   > [!NOTE]
   > Varsa **MFC uygulaması** türü eksik:<br/>
   > **Visual Studio 2017**: Seçin **açık Visual Studio yükleyicisi** sol bölmesinde **yeni proje** iletişim kutusu. Yükle seçeneği altında bulunan **C++ ile masaüstü geliştirme** içinde **isteğe bağlı** adlı bileşenleri bölümünde **x86 ve x64 için Visual C++ MFC**.<br/>
   > **Visual Studio 2015**: Windows Başlat düğmesini ve türü **Program Ekle/Kaldır**. Sonuç listesinden programını açın ve Microsoft Visual Studio 2015 yüklemenizi yüklü programlar listesinde bulun. Çift tıklayın ve ardından **Değiştir** seçip **Microsoft Foundation sınıfları** altındaki bileşen **Visual C++**.

1. İçin etkin çözüm yapılandırmasını değiştirme **yayın**. Gelen **derleme** menüsünde **Yapılandırma Yöneticisi'ni**. Gelen **Configuration Manager** iletişim kutusunda **yayın** gelen **etkin çözüm yapılandırması** açılan kutusu. **Kapat**'ı tıklatın.

1. Tuşuna **Ctrl**+**Shift**+**B** uygulamayı oluşturmak için. Veya **derleme** menüsünü tıklatın **Çözümü Derle**. Uygulama oluşturma, bu MFC uygulaması projesinin çıktı kullanılacak Kurulum projesi sağlar.

1. Zaten yapmadıysanız, Microsoft Visual Studio yükleyici projeleri uzantısını indirin. Uzantı, Visual Studio geliştiricileri için ücretsizdir ve Visual Studio için Kurulum ve dağıtım proje şablonları işlevselliğinin ekler. Visual Studio'da, İnternete bağlı olduğunuzda seçin **Araçları** > **Uzantılar ve güncelleştirmeler**. Altında **Uzantılar ve güncelleştirmeler** iletişim kutusunda **çevrimiçi** sekmesi ve türü *Microsoft Visual Studio yükleyici projeleri* arama kutusuna. İsabet **Enter**seçin **Microsoft Visual Studio \<sürüm > yükleyici projeleri**, tıklatıp **indirme**. Tercih çalıştırın ve uzantıyı yükledikten sonra Visual Studio'yu yeniden başlatın.

1. Menü çubuğunda, **dosya** > **son projeler ve çözümler**, projenizi yeniden seçin.

1. Menü çubuğunda, **dosya** > **yeni** > **proje** açmak için **yeni proje** iletişim kutusu. İletişim kutusunun sol bölmesinde genişletin **yüklü** > **diğer proje türleri** düğümleri ve select **Visual Studio yükleyicisi**. Orta bölmede seçin **Kurulum projesi**.

1. Kurum projesi için bir ad girin **adı** kutusu. İçinde **çözüm** aşağı açılan listesinden **eklemek için çözüm**. Seçin **Tamam** Kurulum projesi oluşturmak için. A **dosya Yardımcısı (ProjectName)** sekmesi düzenleyici penceresinde açılır.

1. Sağ **uygulama klasörü** düğümünü seçip alt **Ekle** > **proje çıktısı** açmak için **proje çıkış grubu Ekle**iletişim kutusu. İletişim kutusunda **birincil çıkışının** tıklatıp **Tamam**. Adlı yeni bir öğe **birincil (etkin) ProjectName çıktısını** görünür.

1. Sağ **uygulama klasörü** düğümünü seçip alt **Ekle** > **derleme** açmak için **bileşen seçin** iletişim bir kutu. Seçip makalesiyle açıklandığı şekilde program tarafından gereken DLL'leri gerekli ekleyin [belirleme hangi DLL'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md).

1. Öğeyi seçin **birincil (etkin) ProjectName çıktısını**seçin ve sağ tıklatıp **oluşturma kısayoldan birincil çıktı ProjectName (etkin)**. Adlı yeni bir öğe **ProjectName (etkin) için birincil çıkışının kısayoldan** görünür. Kısayol öğeyi yeniden adlandır sonra sürükleyip öğesine **kullanıcının Programlar menüsü** pencerenin sol tarafındaki düğümü.

1. Menü çubuğunda, **derleme** > **Configuration Manager**. İçinde **proje** tablosuna ve altında **derleme** sütun, dağıtım projesi için kutuyu işaretleyin. **Kapat**'ı tıklatın.

1. Menü çubuğunda, **derleme** > **Çözümü Derle** MFC projesi ve dağıtım projesi oluşturun.

1. Çözüm klasöründe dağıtım tarafından oluşturulan setup.exe programını bulun. Uygulama ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosyayı (ve .msi dosyasını) kopyalayabilirsiniz. Kurulum programı, Visual C++ kitaplıkları sahip ikinci bir bilgisayarda çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[Dağıtım Örnekleri](deployment-examples.md)<br/>

---
title: 'İzlenecek Yol: Programınızı Dağıtma (C++)'
ms.date: 09/14/2018
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
ms.openlocfilehash: 43e6b9320fb52fc17f65b27b06e2c6f4d4851528
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496440"
---
# <a name="walkthrough-deploying-your-program-c"></a>İzlenecek Yol: Programınızı Dağıtma (C++)

Listelenen önceki izlenecek yolları, tamamlayarak uygulamanızı oluşturdunuz [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md), böylece diğer kullanıcıların bir yükleyici oluşturmak için son adımdır programı kendi bilgisayarlarına yükleyin. Yükleyici için varolan çözümünüze yeni bir proje ekleyeceksiniz. Bu yeni proje çıktısı uygulamanız başka bir bilgisayara yükleyecek bir setup.exe dosyasıdır.

İzlenecek yol, uygulamanızı dağıtmak için Windows Installer kullanmayı gösterir. Bir uygulamayı dağıtmak için ClickOnce da kullanabilirsiniz. Daha fazla bilgi için [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md). Genel olarak, dağıtım hakkında daha fazla bilgi için bkz [uygulamaları dağıtma, hizmetleri ve bileşenleri](/visualstudio/deployment/deploying-applications-services-and-components).

## <a name="prerequisites"></a>Önkoşullar

- İzlenecek yol, C++ dili temellerini anladığınızı varsayar.

- Ayrıca, listelenen önceki izlenecek yolları tamamladığınız varsayılır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

- İzlenecek yol, Visual Studio'nun Express sürümlerinde tamamlanamaz.

- Zaten yapmadıysanız, başka bir adım daha sonra açıklandığı gibi Microsoft Visual Studio yükleyici projeleri uzantısını indirin. Uzantı, Visual Studio geliştiricileri için ücretsizdir ve Visual Studio için Kurulum ve dağıtım proje şablonları işlevselliğinin ekler.

### <a name="to-install-the-visual-studio-setup-and-deployment-project-template"></a>Visual Studio Kurulum ve dağıtım proje şablonunu yüklemek için

1. Visual Studio'da, İnternete bağlı olduğunuzda seçin **Araçları** > **Uzantılar ve güncelleştirmeler**.

1. Altında **Uzantılar ve güncelleştirmeler**seçin **çevrimiçi** sekmesi ve türü *Microsoft Visual Studio yükleyici projeleri* arama kutusuna. İsabet **Enter**seçin **Microsoft Visual Studio \<sürüm > yükleyici projeleri**, tıklatıp **indirme**.

1. Uzantıyı yükledikten sonra Visual Studio'yu yeniden başlatın, bu seçeneği seçin.

1. Menü çubuğunda, **dosya** > **son projeler ve çözümler**ve ardından **Game** yeniden açmak için çözüm.

### <a name="to-create-a-setup-project-and-install-your-program"></a>Bir kurulum projesi oluşturmak ve programınızı yüklemek için

1. Etkin çözüm yapılandırmasını Release olarak değiştirin. Menü çubuğunda, **derleme** > **Configuration Manager**. İçinde **Configuration Manager** iletişim kutusundaki **etkin çözüm yapılandırması** aşağı açılan listesinden **yayın**. Seçin **Kapat** yapılandırmayı kaydetmek için düğme.

1. Menü çubuğunda, **dosya** > **yeni** > **proje** açmak için **yeni proje** iletişim kutusu.

1. İletişim kutusunun sol bölmesinde **yüklü** > **diğer proje türleri** düğümleri ve ardından **Visual Studio yükleyicisi**. Orta bölmede seçin **Kurulum projesi**.

1. Kurum projesi için bir ad girin **adı** kutusu. Bu örnekte, girin *oyun yükleyici*. İçinde **çözüm** aşağı açılan listesinden **eklemek için çözüm**. Seçin **Tamam** Kurulum projesi oluşturmak için. A **dosya Yardımcısı (oyun Yükleyici)** sekmesi düzenleyici penceresinde açılır.

1. Sağ **uygulama klasörü** düğümünü seçip alt **Ekle** > **proje çıktısı** açmak için **proje çıkış grubu Ekle**iletişim kutusu.

1. İletişim kutusunda **birincil çıkışının** tıklatıp **Tamam**. Adlı yeni bir öğe **Game (etkin) birincil çıkışı** görünür.

1. Öğeyi seçin **birincil (etkin) oyun çıktısını**seçin ve sağ tıklatıp **oluşturma kısayoldan birincil çıkış için oyun (etkin)**. Adlı yeni bir öğe **Game (etkin) için birincil çıkışının kısayoldan** görünür.

1. Kısayol öğeyi yeniden adlandır *oyun*ardından sürükleyip öğesine **kullanıcının Programlar menüsü** pencerenin sol tarafındaki düğümü.

1. İçinde **Çözüm Gezgini**seçin **oyun yükleyici** projesini ve ardından **görünümü** > **Özellikler penceresi** veya isabet **F4** açmak için **özellikleri** penceresi.

1. Yükleyicide görünmesini istediğiniz kadar ek ayrıntıları belirtin.  Örneğin, *Contoso* için **üretici**, *oyun yükleyici* için **ürün adı**, ve *http://www.contoso.com* için **SupportUrl**.

1. Menü çubuğunda, **derleme** > **Configuration Manager**. İçinde **proje** tablosuna ve altında **derleme** sütun için kutuyu **oyun yükleyici**. **Kapat**'ı tıklatın.

1. Menü çubuğunda, **derleme** > **Çözümü Derle** oyun projesini ve oyun yükleyici projesini derlemek için.

1. Çözüm klasöründe, oyun yükleyici tarafından oluşturulan setup.exe programını bulun ve ardından oyun uygulamasını bilgisayarınıza yüklemek için çalıştırın. Uygulama ve gerekli kitaplık dosyalarını başka bir bilgisayara yüklemek için bu dosya (ve GameInstaller.msi) kopyalayabilirsiniz.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [izlenecek yol: bir projenin (C++)](../ide/walkthrough-debugging-a-project-cpp.md)<br/>

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>
[Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)<br/>

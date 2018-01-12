---
title: "İzlenecek yol: Programınızı (C++) dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce59dc7b767c8ff8e988ac7a765d3bb5f1cdfffc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-your-program-c"></a>İzlenecek Yol: Programınızı Dağıtma (C++)
İçinde listelenen önceki ilgili incelemeleri tamamlayarak uygulamanızı oluşturduğunuza göre [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md), diğer kullanıcılar bir yükleyici oluşturmak üzere son adımdır program bilgisayarlarına yükleyin. Bunu yapmak için var olan çözümünüzü yeni bir proje ekleyeceksiniz. Bu yeni proje çıktısı, uygulamanızın başka bir bilgisayara yükler setup.exe dosyasıdır.  
  
 Bu kılavuzda Windows Installer uygulamanızı dağıtmak için nasıl kullanılacağını gösterir. Bir uygulamayı dağıtmak için ClickOnce de kullanabilirsiniz. Daha fazla bilgi için bkz: [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md). Genel olarak, dağıtımı hakkında daha fazla bilgi için bkz [dağıtma uygulamaları, hizmetleri ve bileşenleri](/visualstudio/deployment/deploying-applications-services-and-components).  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Bu kılavuz, C++ dil temelleri anladığınızı varsayar.  
  
-   Ayrıca listelenen ilgili daha önce izlenecek tamamladığınızı varsaymaktadır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
-   Bu kılavuz, Visual Studio Express sürümlerini tamamlanamıyor.  
  
-   Zaten yapmadıysanız, InstallShield Limited Edition (işle), adımlar bu makalenin sonraki bölümlerinde açıklandığı gibi indirin. İşle Visual Studio geliştiricileri için ücretsizdir ve Visual Studio'nun önceki sürümleri Kurulum ve dağıtım proje şablonlarını işlevselliğini değiştirir.  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>İşle Kurulum ve dağıtım proje şablonu yüklemek için  
  
1.  Menü çubuğunda, internet bağlıyken seçin **dosya**, **yeni**, **proje** açmak için **yeni proje** iletişim kutusu.  
  
2.  İletişim kutusunun sol bölmesinde, **yüklü**, **şablonları**, ve **diğer proje türleri** düğümleri ve ardından **Kurulum ve dağıtım**. Orta bölmede seçin **etkinleştirmek InstallShield Limited Edition** ve ardından **Tamam** düğmesi.  
  
3.  Visual Studio (işle için) InstallShield Limited Edition'ı yüklemek için yönergeleri izleyin.  
  
4.  İndirdiğiniz, yüklü ve işle etkinleştirilmiş sonra Visual Studio'yu kapatın ve yeniden açın.  
  
5.  Menü çubuğunda seçin **dosya**, **yeni projeler ve çözümler**ve ardından **oyun** çözümü yeniden açın.  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>Kurulum projesi oluşturup, programı yüklemek için  
  
1.  Etkin çözüm yapılandırması yayın olarak değiştirin. Menü çubuğunda seçin **yapı**, **Configuration Manager**. İçinde **Configuration Manager** iletişim kutusundaki **etkin çözüm yapılandırması** aşağı açılan listesinden, **sürüm**. Seçin **Kapat** yapılandırmayı kaydetmek için düğmesi.  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** açmak için **yeni proje** iletişim kutusu.  
  
3.  İletişim kutusunun sol bölmesinde, **yüklü**, **şablonları**, ve **diğer proje türleri** düğümleri ve ardından **Kurulum ve dağıtım**. Orta bölmede seçin **InstallShield Limited Edition proje**.  
  
4.  Kurulum projesi için bir ad girin **adı** kutusu. Bu örnekte, girin **oyun yükleyici**. İçinde **çözüm** aşağı açılan listesinden, **eklemek için çözüm**. Seçin **Tamam** düğmesi Kurulum projesi oluşturun. A **proje Yardımcısı (oyun Yükleyici)** sekmesi Düzenleyicisi penceresinde açılır.  
  
5.  Ekranın alt kısmındaki **proje Yardımcısı (oyun Yükleyici)** sekmesinde, seçin **uygulama bilgilerini** bağlantı.  
  
6.  Üzerinde **uygulama bilgilerini** sayfasında, yükleyici görünmesini istediğiniz gibi şirketinizin adını belirtin. Şirketinizin adını kullanın veya bu örneğin **Contoso**. Uygulama adınız; belirtin. Bu örnekte belirtin **oyun**. Şirketinizin web adresini belirtin veya bu örneğin **http://www.contoso.com**.  
  
7.  Ekranın alt kısmındaki **proje Yardımcısı (oyun Yükleyici)** sekmesinde, seçin **yükleme görüşme** bağlantı.  
  
8.  Üzerinde **yükleme görüşme** sayfasında, altında **, Lisans Sözleşmesi iletişim kutusunu görüntülemek istediğiniz**seçin **Hayır** seçenek düğmesi. Altında **istemi kullanıcıların kendi şirket adını girin ve kullanıcı adı istediğiniz**seçin **Hayır** seçenek düğmesi.  
  
9. İçinde **Çözüm Gezgini**, genişletin **oyun yükleyici** projesi, genişletin **düzenlemek bilgisayarınızı Kurulum** düğümünü ve ardından açın **genel bilgiler** sayfası.  
  
10. Üzerinde **genel bilgiler (oyun Yükleyici)** sekmesinde Düzenleyicisi penceresinde, belirtin bir **etiketi Oluşturucu Kimliği**, örneğin, **regid.2012 12.com.Contoso**.  
  
11. İçinde **Çözüm Gezgini**altında **oyun yükleyici** projesi, genişletin **uygulama verilerini belirtin** düğümünü ve ardından açın **dosyaları** Sayfa.  
  
12. Üzerinde **dosyaları (oyun Yükleyici)** Düzenleyicisi penceresinde, altında sekmesinde **bilgisayarın dosyalarını kaynağı**, kısayol menüsünü açın **birincil çıktı gelen oyun** ve seçin**Kopya**.  
  
13. Alanı altında bir kısayol menüsü açma **adı** sütununda **hedef bilgisayarın dosyaları**ve seçin **Yapıştır**. Adlı yeni bir öğe **Game.Primary çıkış** görüntülenir.  
  
14. İçinde **Çözüm Gezgini**altında **uygulama verilerini belirtin** düğümü, açık **yeniden dağıtılabilir öğeleri** sayfası.  
  
15. Üzerinde **yeniden dağıtılabilir öğeleri (oyun Yükleyici)** Düzenleyicisi penceresinde, seçin sekmesinde **Visual C++ 11.0 CRT (x86)** onay kutusu.  
  
16. Menü çubuğunda seçin **yapı**, **yapı çözümü** oyun proje ve oyun yükleyici proje oluşturmak için.  
  
17. Çözüm klasöründe oyun yükleyici projesinden oluşturulan setup.exe programını bulun ve ardından oyun uygulaması bilgisayarınıza yüklemek için çalıştırın. Uygulamayı yüklemek için bu dosyayı ve başka bir bilgisayarda gerekli kitaplık dosyalarını kopyalayabilirsiniz.  
  
18. Birçok seçenek gereksinimlerinize uyacak şekilde Kurulum projesi ayarlayabilirsiniz. Daha fazla bilgi için içinde **Çözüm Gezgini**altında **oyun yükleyici** proje, açık **Başlarken** sayfasında ve işle Yardım Kitaplığı'nı açmak için F1 tuşuna'i seçin.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [izlenecek yol: bir projenin (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)  
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)
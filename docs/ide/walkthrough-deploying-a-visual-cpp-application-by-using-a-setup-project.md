---
title: Kurulum projesi kullanarak Visual C++ uygulamasını dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 454507a3a3f33b43af0e50c25dab6703aa75a56b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33332786"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>İzlenecek Yol: Kurulum Projesi Kullanarak Visual C++ Uygulamasını Dağıtma
Kurulum projesi Visual C++ uygulamasını dağıtmak için nasıl kullanılacağını açıklar.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Bir bilgisayarla [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] yüklü.  
  
-   Visual C++ kitaplıkları bulunmayan başka bir bilgisayar.  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>Kurulum projesi kullanarak bir uygulamayı dağıtmak için  
  
1.  Kullanım **MFC ApplicationWizard** yeni bir Visual Studio çözümü oluşturmak için. Gelen Sihirbazı'nı bulmak için **yeni proje** iletişim kutusunda, genişletin **Visual C++** düğümü, select **MFC**seçin **MFC uygulaması**, girin bir Proje için adı ve ardından **Tamam**.  
  
2.  Etkin çözüm yapılandırmasını değiştirme **sürüm**. Gelen **yapı** menüsünde, select **Configuration Manager**. Gelen **Configuration Manager** iletişim kutusunda **sürüm** gelen **etkin çözüm yapılandırması** açılan kutusu.  
  
3.  Uygulamayı yapılandırmak için F7 tuşuna basın. Veya, **yapı** menüsünde tıklatın **yapı çözümü**. Bu, bu MFC Uygulama projesi çıktısını kullanmak kurulum projesi sağlar.  
  
4.  Zaten yapmadıysanız, InstallShield Limited Edition (Visual Studio geliştiricileri için boş olan ve Kurulum ve dağıtım için Visual Studio Proje şablonları işlevselliğini değiştirir işle), indirin. Internet'e bağlı açtığınızda **yeni proje** seçerek iletişim kutusu **dosya**, **yeni**, **proje** çubuğu ya da tarafından menüsünde Çözümünüze sağ **Çözüm Gezgini** ve seçme **Ekle**, **yeni proje**. Genişletin **diğer proje türleri** düğümü seçin **InstallShield Limited Edition etkinleştirmek** içinde **Kurulum ve dağıtım** düğümü, gösterilen yönergeleri izleyin. İndirdiğiniz, yüklü ve etkinleştirilmiş InstallShield Limited Edition sonra Visual Studio'yu kapatın ve yeniden açın.  
  
5.  Açık **yeni proje** iletişim kutusunu yeniden genişletin **diğer proje türleri** düğümü ve seçin **InstallShield Limited Edition proje** içinde  **InstallShield Limited Edition** düğümü.  
  
6.  ' Ndaki yönergeleri izleyin **Başlarken** bir çıkış başvurusu Visual Studio MFC projenize eklemek için InstallShield Limited Edition şablonu tarafından oluşturulan Kurulum proje düğümünün.  
  
7.  Yükleyici dosyasını (setup.exe) oluşturmak için Kurulum projesi oluşturun. Bunu yapmak için sağ Kurulum proje düğümüne tıklayın **Çözüm Gezgini** seçip **yapı**.  
  
     InstallShield Limited Edition'ın kurulum projesi ağacında kurulum dosyası oluşturur (varsayılan olarak, bu kurulum projesi Express\SingleImage\DiskImages\DISK1 alt klasöründe bulunabilir).  
  
8.  Kurulum programı Visual C++ kitaplıkları yok ikinci bir bilgisayarda çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dağıtım Örnekleri](../ide/deployment-examples.md)
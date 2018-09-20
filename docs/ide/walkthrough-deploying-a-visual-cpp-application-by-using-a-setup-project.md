---
title: Bir kurulum projesi kullanarak Visual C++ uygulamasını dağıtma | Microsoft Docs
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
ms.openlocfilehash: a9e781a311f965dc71bb64425a4d1354d6b38e1a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416571"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>İzlenecek Yol: Kurulum Projesi Kullanarak Visual C++ Uygulamasını Dağıtma

Visual C++ uygulaması dağıtmak için bir kurulum projesi kullanmayı açıklar.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Visual Studio 2012 yüklü olan bir bilgisayar.

- Visual C++ kitaplıkları yok. başka bir bilgisayar.

### <a name="to-deploy-an-application-by-using-a-setup-project"></a>Bir kurulum projesi kullanarak bir uygulamayı dağıtmak için

1. Kullanım **MFC ApplicationWizard** yeni bir Visual Studio çözümü oluşturmak için. Sihirbaz bulmalarına için **yeni proje** iletişim kutusunda **Visual C++** düğümünü **MFC**seçin **MFC uygulaması**, girin bir Projeyi adlandırın ve ardından **Tamam**.

1. İçin etkin çözüm yapılandırmasını değiştirme **yayın**. Gelen **derleme** menüsünde **Yapılandırma Yöneticisi'ni**. Gelen **Configuration Manager** iletişim kutusunda **yayın** gelen **etkin çözüm yapılandırması** açılan kutusu.

1. Uygulamayı oluşturmak için F7'ye basın. Veya **derleme** menüsünü tıklatın **Çözümü Derle**. Bu çıktı bu MFC uygulaması projesinin kullanılacak Kurulum projesi sağlar.

1. Zaten yapmadıysanız, InstallShield Limited Edition (Visual Studio geliştiricileri için ücretsizdir ve Kurulum ve dağıtım için Visual Studio Proje şablonları işlevselliğinin yerine geçer ısle) programını indirin. Internet'e bağlıyken açın **yeni proje** iletişim kutusunu **dosya**, **yeni**, **proje** çubuk veya tarafından menüsünde çözümünüzde sağ **Çözüm Gezgini** seçip **Ekle**, **yeni proje**. Genişletin **diğer proje türleri** düğümünü seçin **InstallShield Limited Edition'ı Etkinleştir** içinde **Kurulum ve dağıtım** düğümünü ve görüntülenen yönergeleri izleyin. İndirdiğiniz, yüklü ve etkin InstallShield Limited Edition sonra Visual Studio'yu kapatın ve yeniden açın.

1. Açık **yeni proje** iletişim kutusu yeniden genişletin **diğer proje türleri** düğümünü seçip **InstallShield Limited Edition projesi** içinde  **InstallShield Limited Edition** düğümü.

1. Yönergeleri **Başlarken** Visual Studio MFC projenize bir çıkış başvurusu eklemek için InstallShield Limited Edition şablonu tarafından oluşturulan Kurulum projesi düğümü.

1. (Setup.exe) yükleyici dosyası oluşturmak için Kurulum projesi oluşturun. Bunu yapmak için sağ, Kurulum projesi düğümünü tıklatın **Çözüm Gezgini** seçip **yapı**.

   InstallShield Limited Edition, Kurulum proje ağacında, kurulum dosyası oluşturur (varsayılan olarak, Kurulum projesini Express\SingleImage\DiskImages\DISK1 alt klasöründe bulunabilir).

1. Kurulum programı, Visual C++ kitaplıkları sahip ikinci bir bilgisayarda çalıştırın.

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım Örnekleri](../ide/deployment-examples.md)
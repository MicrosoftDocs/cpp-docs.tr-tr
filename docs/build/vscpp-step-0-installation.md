---
title: Visual Studio 2017'de C++ desteği yükleme
description: Visual C++ için Visual Studio desteği yükleme
ms.custom: mvc
ms.date: 11/19/2018
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: ac8439e1709b6bbce6f32580bafee50c9ff30e3f
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977751"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio'da C++ desteği yükleme

İndirilen ve henüz Visual Studio 2017 ve Visual C++ Araçları yüklü olmayan, kullanmaya nasıl başlayacağınızı aşağıda verilmiştir.

## <a name="prerequisites"></a>Önkoşullar

- Geniş bant internet bağlantısı. Visual Studio yükleyicisinin birçok gigabayta kadar veri indirebilirsiniz.

- Microsoft Windows 7 veya sonraki sürümleri çalıştıran bir bilgisayar. Windows 10 için en iyi geliştirme deneyimi öneririz. Visual Studio yüklemeden önce en son güncelleştirmeleri sisteminize uygulandığından emin olun.

- Yeterli boş disk alanı. Visual Studio, en az 7 GB disk alanı gerektirir ve birçok ortak seçenekleri yüklüyse, 50 GB veya daha fazla sürebilir. C: sürücünüzde yüklemeniz önerilir.

Disk alanı ve işletim sistemi gereksinimleri hakkında daha fazla bilgi için bkz: [Visual Studio ürün ailesi sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs). Yükleyici seçenekleri için ne kadar disk alanı gereklidir bildirir.

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 yüklemesi

Visual Studio 2015'i yüklemek için Git [Visual Studio'nun eski sürümlerini indirin](https://www.visualstudio.com/vs/older-downloads/). Kurulum programını çalıştırın ve seçin **özel yükleme** C++ bileşeni seçin. Mevcut bir Visual Studio 2015 yüklemesini C++ desteği eklemek için Windows Başlat düğmesini türü tıklayın ve **Program Ekle/Kaldır**. Sonuç listesinden programını açın ve ardından Visual Studio 2015 yüklemenizi yüklü programlar listesinde bulun. Çift tıklayın ve ardından **Değiştir** ve yüklemek için Visual C++ bileşenleri seçin.

Genel olarak, Visual Studio 2015 derleyici kullanarak kodunuzu derlemek için ihtiyacınız olsa bile, Visual Studio 2017 kullanmanızı öneririz. Daha fazla bilgi için [yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanmak](../porting/use-native-multi-targeting.md).

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 yüklemesi

1. Windows için en son Visual Studio 2017 Yükleyicisi'ni indirin.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community'yi yükleyin](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Topluluk sürümü bireysel geliştiriciler, sınıfta öğrenim ortamı, akademik araştırma ve açık kaynak geliştirme için ' dir. Diğer kullanımlar için yükleme [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) veya [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

1. Yükleyici dosyasını indirdiğiniz ve uygulamayı bulun. Tarayıcınızda görüntülenebilir veya indirilenler klasörünüze fark edebilirsiniz. Yükleyiciyi çalıştırmak için yönetici ayrıcalıkları gerekir. Görebileceğiniz bir **kullanıcı hesabı denetimi** seçin; sisteminize değişiklik kurucusunun izni vermek isteyen bir iletişim **Evet**. Sorun yaşıyorsanız, dosya Gezgini'nde indirilen dosyayı bulmak, yükleyici simgesini sağ tıklatın ve seçin **yönetici olarak çalıştır** bağlam menüsünden.

   ![Visual Studio Yükleyicisi'nin karşıdan yükleyip](../build/media/vscpp-concierge-run-installer.gif "indirip Visual Studio Yükleyicisi'ni yükleyin")

1. Yükleyici belirli geliştirme alanlar için ilgili seçenekleri gruplarıdır iş yüklerinin bir listesini sunar. Podporu iOS Pro C++ artık varsayılan olarak yüklü değildir isteğe bağlı iş yüklerinin parçasıdır.

   ![C++ iş yükünde ile masaüstü geliştirme](../build/media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

   C++ için seçin **C++ ile masaüstü geliştirme** iş yükü ve ardından **yükleme**.

   ![Masaüstü uygulama geliştirme ile C++ iş yükünü yükleyin](../build/media/vscpp-concierge-choose-workload.gif "Masaüstü uygulama geliştirme ile C++ iş yükünü yükleyin.")

1. Yükleme tamamlandığında seçin **başlatma** Visual Studio'yu başlatmak için düğme.

   Visual Studio'yu çalıştırdığınız ilk kez Microsoft Account oturum açmaları istenir. Yoksa, bir ücretsiz oluşturabilirsiniz. Ayrıca, bir tema seçmeniz gerekir. Endişelenmeyin, isterseniz, daha sonra değiştirebilirsiniz.

   Birçok Visual Studio sürebilir hazır hale getirmek için dakika, onu çalıştırdığınız ilk kez kullanın. İşte bu şekilde bir hızlı atlamalı görünür:

   ![Visual Studio 2017 oturum](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017 oturum açın")

   Yeniden çalıştırdığınızda visual Studio çok daha hızlı başlatılır.

1. Visual Studio açıldığında başlık çubuğunda bayrak simgesine vurgulanır denetleyin:

   ![Visual Studio 2017 bildirim bayrağı](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 bildirim bayrağı")

   Vurgulanır, açmak için seçmeniz **bildirimleri** penceresi. Visual Studio için kullanılabilen herhangi bir güncelleştirme varsa, artık yüklemeniz kesinlikle önerilir. Yükleme tamamlandıktan sonra Visual Studio'yu yeniden başlatın.

Visual Studio çalışırken, sonraki adıma devam etmek hazır olursunuz.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

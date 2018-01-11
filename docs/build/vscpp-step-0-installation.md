---
title: "Visual Studio'da C++ desteği yükleme | Microsoft Docs"
description: "Visual C++ için Visual Studio desteğini yükleme"
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b895569e5535fb05c1e2383df224f149815dd47f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio'da C++ desteğini yükleme

İndirilen ve henüz yüklü Visual Studio ve Visual C++ Araçları yüklemediyseniz, nasıl başlayacağınızı aşağıda verilmiştir.

## <a name="prerequisites"></a>Önkoşullar

- Geniş bant internet bağlantısı. Visual Studio yükleyicisi birkaç gigabayt veri indirebilirsiniz.

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 öneririz. Visual Studio yüklemeden önce en son güncelleştirmeleri sisteminize uygulanan emin olun.

- Yeterli boş disk alanı. Visual Studio en az 7 GB disk alanı gerektirir ve birçok yaygın seçenekler yüklediyseniz 50 GB veya daha fazla sürebilir. C: sürücünüzde yüklemeniz önerilir.

Disk alanı ve işletim sistemi gereksinimleri hakkında daha fazla bilgi için bkz: [Visual Studio 2017 sistem gereksinimleri](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs). Yükleyici seçenekleri için ne kadar disk alanı gereklidir bildirir.

## <a name="installation"></a>Yükleme

1. Windows için en son Visual Studio 2017 yükleyicisi indirin.

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Community yükle</a>

   >[!Tip]
   > Community edition her bir geliştirici, sınıf öğrenme, akademik araştırma ve açık kaynak geliştirme içindir. Diğer kullanımlar için yükleme <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Professional</a> veya <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Enterprise</a>.

1. Karşıdan yükleyip çalıştırın yükleyici dosyasını bulun. Tarayıcınızda görüntülenebilir veya yüklemeleri klasörünüzdeki bulabilirsiniz. Yükleyiciyi çalıştırmak için yönetici ayrıcalıkları gerekiyor. Görebileceğiniz bir **kullanıcı hesabı denetimi** sisteminize değişiklik; seçin yükleyici izin izni vermek isteyen iletişim **Evet**. Sorun yaşıyorsanız, indirilen dosyayı dosya Gezgini'nde bulmak, yükleyici simgesine sağ tıklayın ve seçin **yönetici olarak çalıştır** ve bağlam menüsünden.

   ![Visual Studio 2017 yükleyiciyi çalıştırmak](../build/media/vscpp-concierge-run-installer.gif "Visual Studio yükleyiciyi çalıştırın")

1. Yükleyici belirli geliştirme alanlar için ilgili seçenekleri gruplarıdır iş yükleri listesini gösterir. C++ desteği artık varsayılan olarak yüklü değildir isteğe bağlı iş yükleri bir parçasıdır.

   ![C++ ile masaüstü geliştirme](../build/media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

    C++ için seçin **C++ ile masaüstü geliştirme** iş yükü ve ardından **yükleme**.

   ![C++ yüküyle masaüstü geliştirme yüklemek](../build/media/vscpp-concierge-choose-workload.gif "masaüstü geliştirme C++ yüküyle yükleyin")

1. Yükleme tamamlandığında seçin **başlatma** düğmesi Visual Studio'yu başlatın.

   Visual Studio, çalıştırdığınız ilk kez bir Microsoft Account oturum istenir. Yoksa, bir ücretsiz oluşturabilirsiniz. Ayrıca bir tema seçmeniz gerekir. Endişelenmeyin, isterseniz, daha sonra değiştirebilirsiniz. 

   Birkaç Visual Studio sürebilir çok çalıştırmadan ilk kez kullanıma hazır hale getirmek için dakika. İşte bu şekilde bir hızlı zaman atlama görünür:

   ![Visual Studio 2017 oturum](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017 oturum açın")

   Yeniden çalıştırdığınızda, visual Studio çok daha hızlı başlatır.

1. Visual Studio oturum açtığında, bayrak simgesinin başlık çubuğunda vurgulanır denetleyin:

   ![Visual Studio 2017 bildirim bayrağına](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 bildirim bayrağı")

   Vurgulanır değilse, açmak için seçin **bildirimleri** penceresi. Visual Studio için kullanılabilir güncelleştirmeler varsa, şimdi yükle öneririz. Yükleme tamamlandıktan sonra Visual Studio'yu yeniden başlatın.

Visual Studio çalıştırırken, sonraki adıma devam etmek hazır olursunuz.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

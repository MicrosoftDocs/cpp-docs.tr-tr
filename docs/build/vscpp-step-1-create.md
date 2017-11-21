---
title: "Adım 1 - bir C++ konsol uygulama projesi oluşturun. | Microsoft Docs"
description: "Visual C++ için Visual Studio desteğini yükleme"
ms.custom: mvc
ms.date: 10/17/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f75d8fc6ec744038d57bfb7576547c9be84b7551
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

Normal başlangıç noktası C++ programcı için bir "Hello, world!" komut satırı üzerinde çalışan uygulama. Ne Visual Studio'da bu adımda oluşturacağınız olmasıdır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio masaüstü geliştirme ile yüklenmiş ve bilgisayarınızda çalışan C++ iş yükü var. Henüz yüklü değilse bkz [adım 0 - Visual Studio yükleme C++ Destek](../build/vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Uygulama projesi oluşturma

Visual Studio kullanan *projeleri* bir uygulama kodunu düzenlemenizi ve *çözümleri* projelerinizi düzenlemek için. Bir proje tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir ve projenin tüm dosyaları ve dış dosyaları arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için ilk olarak, yeni proje ve çözüm oluşturacaksınız.

1. Visual Studio'da açın **dosya** menü ve **yeni > Proje** açmak için **yeni proje** iletişim.

   ![Yeni Proje iletişim kutusunu açmak](../build/media/vscpp-file-new-project.gif "yeni proje iletişim kutusunu aç")

1. İçinde **yeni proje** iletişim kutusunda **yüklü**, **Visual C++** seçili değilse ve ardından seçerseniz **boş proje** Şablon. İçinde **adı** alanına, *HelloWorld*. Seçin **Tamam** projesi oluşturmak için.

   ![Ad ve yeni proje oluşturma](../build/media/vscpp-concierge-project-name-callouts.png "adı ve yeni proje oluşturma")

Visual Studio yeni, boş proje oluşturma ve kaynak kodu dosyaları eklemek için istediğiniz uygulama türü için özelleştirmek üzere hazır oluşturur. Bu sonraki gerçekleştirirsiniz.

[I bir sorunla karşılaştık.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Bir konsol uygulaması projeniz olun

Visual Studio, Windows ve diğer platformlar için her türlü uygulamaları ve bileşenleri oluşturabilirsiniz. **Boş proje** şablon ne tür bir uygulama oluşturur hakkında belirli değil. Oluşturmak için bir *konsol uygulaması*, bir çalışan bir konsol veya komut istemi penceresinde, konsol alt sistemi kullanmak için uygulamanızı oluşturmak için Visual Studio bildirmeniz gerekir.

1. Visual Studio'da açın **proje** menü ve **özellikleri** açmak için **HelloWorld özellik sayfaları** iletişim.

1. İçinde **özellik sayfaları** iletişim altında **yapılandırma özellikleri**seçin **bağlayıcı**, **sistem**ve ardından düzenleme kutusuna seçin **alt sistemi** özelliği. Görüntülenen açılır menüde seçin **konsol (/ SUBSYSTEM: KONSOL)**. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

   ![Özellik sayfaları iletişim kutusunu açmak](../build/media/vscpp-properties-linker-subsystem.gif "özellik sayfaları iletişim kutusunu aç")

Visual Studio konsol penceresinde çalıştırmak için projeyi derlemek için şimdi bilir. Ardından, bir kaynak kodu dosyasına ekleyin ve uygulamanız için kodu girin.

[I bir sorunla karşılaştık.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Kaynak kodu dosyasına Ekle

1. İçinde **Çözüm Gezgini**, HelloWorld projesini seçin. Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle** açmak için **Yeni Öğe Ekle** iletişim.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **Visual C++** altında **yüklü** zaten seçili değilse. Orta bölmede seçin **C++ dosyasına (.cpp)**. Değişiklik **adı** için *HelloWorld.cpp*. Seçin **Ekle** iletişim kutusunu kapatın ve dosyayı oluşturmak için.

   ![Bir kaynak dosya için HelloWorld.cpp eklemek](../build/media/vscpp-add-new-item.gif "HelloWorld.cpp için bir kaynak dosyası ekleme")

Visual studio yeni, boş kaynak kodu dosyasının oluşturur ve bir Düzenleyicisi penceresinde, kaynak kodu girmek için hazır açar.

[I bir sorunla karşılaştık.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Kodu kaynak dosyasına ekleyin

1. Bu kodu HelloWorld.cpp Düzenleyicisi penceresine kopyalayın.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   Kod Düzenleyicisi penceresinde aşağıdaki gibi görünmelidir:

   ![Hello World Kod düzenleyicisinde](../build/media/vscpp-hello-world-editor.png "Düzenleyicisi'nde Hello World kodu")

Kod Düzenleyicisi'nde şöyle, sonraki adıma geçin ve uygulamanızı oluşturmaya hazırsınız.

[I bir sorunla karşılaştık.](#add-a-source-code-file-issues)

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [2. adım: Derleme ve C++ projesi çalıştırma](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

Burada ilk C++ projenizi oluşturduğunuzda çözümleri için genel sorunlar gelir.

### <a name="create-your-app-project-issues"></a>Proje sorunları uygulamanızı oluşturma

Varsa **yeni proje** değil iletişim kutusunu göster bir **Visual C++** altında girdisi **yüklü**, Visual Studio kopyanızı büyük olasılıkla yok **Masaüstü C++ ile geliştirme** yüklü iş yükü. Yükleyici doğrudan çalıştırabilirsiniz **yeni proje** iletişim. Seçin **açık Visual Studio yükleyicisi** bağlantı Yükleyicisi'ni yeniden başlatın. Varsa **kullanıcı hesabı denetimi** iletişim istekleri izinleri, seçin **Evet**. Yükleyicisi'nde emin olun **C++ ile masaüstü geliştirme** iş yükü denetlenir ve seçin **Tamam** Visual Studio yüklemenizin güncelleştirmek için.

Aynı ada sahip başka bir proje zaten varsa, projeniz için başka bir ad seçin veya varolan projeyi silin ve yeniden deneyin. Varolan projeyi silmek için dosya Gezgini'nde Çözüm klasörü (helloworld.sln dosyasını içeren klasör) silin.

[Geri dönün](#create-your-app-project).

### <a name="make-your-project-a-console-app-issues"></a>Projenizi bir konsol uygulaması sorunları olun

Görmüyorsanız, **bağlayıcı** altında listelenen **yapılandırma özellikleri**, seçin **iptal** kapatmak için **özellik sayfaları** iletişim ve ardından olduğundan emin olun **HelloWorld** proje seçildiğinde, **Çözüm Gezgini**, değil çözüm veya başka bir dosya veya klasör, yeniden denemeden önce.

Aşağı açılan denetim görünmez **alt sistemi** özellik düzenleme kutusuna özelliği seçene kadar. İşaretçinin kullanarak seçim yapabilir veya iletişim kutusu denetimleri kadar dolaşmak için SEKME tuşuna basabilirsiniz **alt sistemi** vurgulanır. Açılır liste denetimi seçin veya açmak için Alt + Aşağı ok tuşlarına basın.

[Geri Git](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Kaynak kodu dosya sorunları Ekle

Kaynak kodu dosyasının farklı bir ad verin, sorun değildir. Ancak, aynı kod projenize içeren birden fazla kaynak kodu dosyasının eklemeyin.

Projeniz için yanlış bir dosya türünü eklediyseniz, örneğin, bir üst bilgi dosyasını silin ve yeniden deneyin. Dosyayı silmek için seçin **Çözüm Gezgini** ve Delete tuşuna basın.

[Geri dönün](#add-a-source-code-file).

### <a name="add-code-to-the-source-file-issues"></a>Kaynak dosya sorunları için kod ekleme

Yeniden açmak için kaynak kodu dosya Düzenleyicisi penceresinde, yanlışlıkla kapattıysanız HelloWorld.cpp çift **Çözüm Gezgini** penceresi.

Kırmızı dalgalı çizgiler kaynak kod düzenleyicisinde herhangi bir şey altında görünmüyorsa, kodunuzu yazımı, noktalama ve servis talebi örnekte eşleşip eşleşmediğini denetleyin. C++ kodu önemli bir durumdur.

[Geri dönün](#add-code-to-the-source-file).

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
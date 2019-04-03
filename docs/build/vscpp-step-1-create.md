---
title: C++ konsol uygulama projesi oluşturma
description: Visual c++'ta bir Hello World konsol uygulaması oluşturma
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 739da0b6e5400117c0b09a3d4c3335bd44529a25
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58898784"
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

Her zamanki başlangıç noktası C++ programcısı için bir "Hello, world!" komut satırı üzerinde çalışan uygulama. Hangi Visual Studio'da bu adımda oluşturacağınız olmasıdır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio ile masaüstü geliştirme, yüklü ve bilgisayarınızda çalışan C++ iş yükünde sahip. Henüz yüklü değilse, bkz. [Visual Studio'da C++ yükleme desteği](vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturun

Visual Studio kullanan *projeleri* bir uygulama için kod düzenleme ve *çözümleri* projelerinizi düzenlemek için. Bir proje, tüm seçenekleri, yapılandırmaları ve uygulamalarınızı oluşturmak için kullanılan kuralları içerir ve tüm proje dosyaları ve dış dosyaları arasındaki ilişki yönetir. Uygulamanızı oluşturmak için ilk olarak, yeni proje ve çözüm oluşturacaksınız.

::: moniker range=">=vs-2019"

1. Visual Studio'da açın **dosya** menüsünü seçip **yeni** > **proje** açmak için **yeni bir proje oluşturun** iletişim. Seçin **konsol uygulaması** şablonu seçip **sonraki**.

   ![Yeni proje oluşturma](media/vs2019-choose-console-app.png "yeni proje iletişim kutusu oluşturma açın")

1. İçinde **yeni projenizi yapılandırın** iletişim kutusunda girin *HelloWorld* içinde **proje adı** düzenleme kutusu. Seçin **Oluştur** projeyi oluşturmak için.

   ![Ad ve yeni proje oluşturma](media/vs2019-configure-new-project-hello-world.png "adı ve yeni proje oluşturma")

   Visual Studio, ekleme ve kaynak kodunuzu düzenleme hazır yeni bir proje oluşturur. Varsayılan olarak, kaynak kodunuzu "Hello World" uygulaması ile konsol uygulaması şablonu doldurur:

   ![Hello World proje IDE'de](media/vs2019-hello-world-code.png "IDE'de proje Merhaba Dünya")

   Kod Düzenleyicisi'nde şuna benzer, sonraki adıma gidin ve uygulamanızı oluşturmaya hazırsınız.

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio'da açın **dosya** menüsünü seçip **yeni > Proje** açmak için **yeni proje** iletişim.

   ![Yeni Proje iletişim kutusu açmak](media/vscpp-file-new-project.gif "yeni proje iletişim kutusunu aç")

1. İçinde **yeni proje** iletişim kutusunda **yüklü**, **Visual C++** zaten seçili değilse ve ardından **boş proje** şablonu. İçinde **adı** alanına *HelloWorld*. Seçin **Tamam** projeyi oluşturmak için.

   ![Ad ve yeni proje oluşturma](media/vscpp-concierge-project-name-callouts.png "adı ve yeni proje oluşturma")

Visual Studio, yeni ve boş proje oluşturmak için ve kaynak kod dosyalarınızı eklemek istediğiniz uygulama türü için özelleştirmek üzere hazır oluşturur. Şimdi yaparsınız.

[Bir sorunla karşılaşırsanız çalıştırdım.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Bir konsol uygulaması projeniz olun

Visual Studio, uygulamaları ve bileşenleri her türlü Windows ve diğer platformlar için oluşturabilirsiniz. **Boş proje** şablon ne tür bir uygulama oluşturur hakkında belirli değil. Oluşturmak için bir *konsol uygulaması*, bir çalışan bir konsol veya komut istemi penceresi içinde konsol alt sistemi kullanmak için uygulamanızı oluşturmak için Visual Studio söylemeniz gerekir.

1. Visual Studio'da açın **proje** menüsünü seçip **özellikleri** açmak için **HelloWorld özellik sayfaları** iletişim.

1. İçinde **özellik sayfaları** iletişim altında **yapılandırma özellikleri**seçin **bağlayıcı**, **sistem**ve ardından düzenleme kutusuna yanındaki seçin **alt** özelliği. Görünen açılır menüde seçin **konsol (/ SUBSYSTEM: CONSOLE)**. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

   ![Özellik sayfaları iletişim kutusu açmak](media/vscpp-properties-linker-subsystem.gif "özellik sayfaları iletişim kutusunu aç")

Konsol penceresinde çalıştırmak üzere projenizi oluşturmak için Visual Studio artık biliyor. Ardından, bir kaynak kodu dosyası ekleyin ve uygulamanız için kodu girin.

[Bir sorunla karşılaşırsanız çalıştırdım.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Bir kaynak kodu dosyası ekleyin

1. İçinde **Çözüm Gezgini**, HelloWorld proje seçin. Menü çubuğunda, **proje**, **Yeni Öğe Ekle** açmak için **Yeni Öğe Ekle** iletişim.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **Visual C++** altında **yüklü** zaten seçili değilse. Orta bölmede seçin **C++ dosyası (.cpp)**. Değişiklik **adı** için *HelloWorld.cpp*. Seçin **Ekle** iletişim kutusunu kapatın ve dosyayı oluşturun.

   ![Kaynak dosya eklemek için HelloWorld.cpp](media/vscpp-add-new-item.gif "HelloWorld.cpp için bir kaynak dosyası ekleme")

Visual studio, yeni ve boş bir kaynak kodu dosyası oluşturur ve bir düzenleyici penceresinde, kaynak kodunuzu girmek için hazır açar.

[Bir sorunla karşılaşırsanız çalıştırdım.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Kaynak dosyaya kod ekleyin

1. Bu kodu HelloWorld.cpp düzenleyici penceresi içine kopyalayın.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   Kod Düzenleyici penceresinde şu şekilde görünmelidir:

   ![Hello World Kod Düzenleyicisi'nde](media/vscpp-hello-world-editor.png "Hello World Kod Düzenleyicisi'nde")

Kod Düzenleyicisi'nde şuna benzer, sonraki adıma gidin ve uygulamanızı oluşturmaya hazırsınız.

[Bir sorunla karşılaşırsanız çalıştırdım.](#add-a-source-code-file-issues)

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [Derleme ve C++ projesi çalıştırma](vscpp-step-2-build.md)

::: moniker range="<=vs-2017"

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

Burada, ilk C++ projenizi oluşturduğunuzda çözümleri için yaygın olarak karşılaşılan sorunlarını gelir.

### <a name="create-your-app-project-issues"></a>Proje sorunları uygulamanızı oluşturma

Varsa **yeni proje** değil iletişim kutusu göstermek bir **Visual C++** altında girdisi **yüklü**, Visual Studio kopyanızın büyük olasılıkla yok **Masaüstü C++ ile geliştirme** iş yükü yüklenmiş. Doğrudan yükleyici çalıştırabileceğiniz **yeni proje** iletişim. Seçin **açık Visual Studio yükleyicisi** yükleyiciyi yeniden başlatmak için bağlantı. Varsa **kullanıcı hesabı denetimi** iletişim istekleri izinleri öğesini **Evet**. Yükleyicide emin **C++ ile masaüstü geliştirme** iş yükü denetlenir ve seçin **Tamam** Visual Studio yüklemenizi güncelleştirmek için.

Aynı ada sahip başka bir proje zaten varsa, projeniz için farklı bir ad seçin veya var olan projeyi silin ve yeniden deneyin. Mevcut bir projeyi silmek için dosya Gezgini'nde Çözüm klasörü (helloworld.sln dosyasını içeren klasör) silin.

[Geri dön](#create-your-app-project).

### <a name="make-your-project-a-console-app-issues"></a>Projenize bir konsol uygulaması sorunlarını olun

Görmüyorsanız **bağlayıcı** altında listelenen **yapılandırma özellikleri**, seçin **iptal** kapatmak için **özellik sayfaları** iletişim ve ardından emin olun **HelloWorld** projenin içinde seçili **Çözüm Gezgini**, çözüm veya başka bir dosya veya değil, yeniden denemeden önce klasörü.

Dropdown denetimi görünmez **alt** özellik düzenleme kutusuna kadar özelliğini seçin. İşaretçiyi kullanarak seçim yapabilir veya iletişim kutusu denetimleri kadar arasında geçiş yapmak için sekmesinde basabilirsiniz **alt** vurgulanır. Aşağı açılır denetimden seçin veya açmak için Alt + Aşağı Ok tuşuna basın.

[Geri git](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Bir kaynak kodu dosyası sorunları ekleme

Kaynak kodu dosyasının farklı bir ad verin, sorun değildir. Ancak, aynı kod projenize içeren birden fazla kaynak kodu dosyası eklemeyin.

Yanlış türde bir dosyayı projenize eklenir, örneğin, bir üst bilgi dosyası silin ve yeniden deneyin. Dosyayı silmek için onu seçip **Çözüm Gezgini** ve Delete tuşuna basın.

[Geri dön](#add-a-source-code-file).

### <a name="add-code-to-the-source-file-issues"></a>Kaynak dosya sorunları için kod ekleyin

Yeniden açmak için kaynak kod dosya Düzenleyicisi penceresi, yanlışlıkla kapattıysanız HelloWorld.cpp çift tıklayarak **Çözüm Gezgini** penceresi.

Kaynak Kod düzenleyicisinde herhangi bir şey altında kırmızı dalgalı çizgiler görünüyorsa, kodunuzun çalışması yazım ve noktalama işaretleri örnekte eşleştiğini kontrol edin. C++ kodunda önemli bir durumdur.

[Geri dön](#add-code-to-the-source-file).

::: moniker-end

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

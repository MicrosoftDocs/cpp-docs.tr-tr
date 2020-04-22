---
title: C++ konsol uygulama projesi oluşturma
description: Visual Studio'da Microsoft C++ kullanarak bir Hello World konsol uygulaması oluşturun.
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 07e88da9a8a3712e1d37e319c29fd25aebce8ea7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749312"
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

Bir C++ programcısı için her zamanki başlangıç noktası "Merhaba, dünya!" komut satırında çalışan uygulama. Bu adımda Visual Studio'da bunu yaratacağınız şey bu.

## <a name="prerequisites"></a>Ön koşullar

- C++ iş yükü yüklü ve bilgisayarınızda çalışan Masaüstü geliştirme ile Visual Studio var. Henüz yüklenmediyse Visual [Studio'da C++ desteği yükle'ye](vscpp-step-0-installation.md)bakın.

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturun

Visual Studio, bir uygulamanın kodunu düzenlemek için *projeler* ve projelerinizi düzenlemek için *çözümler* kullanır. Proje, uygulamalarınızı oluşturmak için kullanılan tüm seçenekleri, yapılandırmaları ve kuralları içerir. Projenin tüm dosyaları ve dış dosyalar arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için öncelikle yeni bir proje ve çözüm oluşturursunuz.

::: moniker range=">=vs-2019"

1. Visual Studio'da **Dosya** menüsünü açın ve **Yeni Proje Oluştur** iletişim kutusunu açmak için Yeni > **Projesi'ni** seçin. **C++**, **Windows**ve **Konsol** etiketleri içeren **Konsol Uygulaması** şablonuna sahip olan Konsol Uygulaması şablonunu seçin ve ardından **İleri'yi**seçin.

   ![Yeni bir proje oluşturma](media/vs2019-choose-console-app.png "Yeni proje oluştur iletişim kutusunu açma")

1. Yeni proje iletişim **günlüğüne Yapılandır'da,** **Project adı** düzenlemesi kutusuna *HelloWorld'u* girin. Projeyi oluşturmak için **Oluştur'u** seçin.

   ![Yeni projeyi adlandırın ve oluşturun](media/vs2019-configure-new-project-hello-world.png "Yeni projeyi adlandırın ve oluşturun")

   Visual Studio yeni bir proje oluşturur. Kaynak kodunuzu eklemenize ve yönetmenize hazırdır. Varsayılan olarak, Konsol Uygulaması şablonu kaynak kodunuzu bir "Hello World" uygulamasıyla doldurur:

   ![IDE Merhaba Dünya projesi](media/vs2019-hello-world-code.png "IDE Merhaba Dünya projesi")

   Kod editörde böyle göründüğünde, bir sonraki adıma geçmeye ve uygulamanızı oluşturmaya hazırsınız.

[Bir sorunla karşılaştım.](#create-your-app-project-issues)

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio'da **Dosya** menüsünü açın ve **Yeni Proje** iletişim kutusunu açmak için Yeni **> Projesi'ni** seçin.

   ![Yeni Proje iletişim kutusunu açma](media/vscpp-file-new-project.gif "Yeni Proje iletişim kutusunu açma")

1. Yeni **Proje** iletişim kutusunda, zaten seçilmemişse **Yüklenilen > Visual C++** seçeneğini belirleyin ve ardından **Boş Proje** şablonunu seçin. **Ad** alanına *HelloWorld*girin. Projeyi oluşturmak için **Tamam'ı** seçin.

   ![Yeni projeyi adlandırın ve oluşturun](media/vscpp-concierge-project-name-callouts.png "Yeni projeyi adlandırın ve oluşturun")

Visual Studio yeni, boş bir proje oluşturur. Oluşturmak istediğiniz uygulama türü için uzmanlaşmak ve kaynak kod dosyalarınızı eklemek için hazırdır. Bundan sonra o işlemi yapacaksınız.

[Bir sorunla karşılaştım.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Projenizi bir konsol uygulaması haline getirin

Visual Studio, Windows ve diğer platformlar için her türlü uygulama ve bileşen oluşturabilir. **Boş Proje** şablonu, ne tür bir uygulama oluşturduğu konusunda özel değildir. *Konsol uygulaması,* konsol veya komut istemi penceresinde çalışan uygulamadır. Bir tane oluşturmak için Visual Studio'ya konsol alt sistemini kullanmak için uygulamanızı oluşturmasını söylemeniz gerekir.

1. Visual Studio'da **Project** menüsünü açın ve **HelloWorld Property Pages** iletişim kutusunu açmak için **Özellikler'i** seçin.

1. Özellik **Sayfaları** iletişim kutusunda, **Bağlayıcı > Sistemi > Yapılandırma Özellikleri'ni**seçin ve ardından Alt **Sistem** özelliğinin yanındaki düzenleme kutusunu seçin. Görünen açılır menüde **Konsol (/SUBSYSTEM:CONSOLE) seçeneğini**belirleyin. Değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

   ![Özellik Sayfaları iletişim kutusunu açma](media/vscpp-properties-linker-subsystem.gif "Özellik Sayfaları iletişim kutusunu açma")

Visual Studio artık bir konsol penceresinde çalıştırmak için projenizi oluşturmak için bilir. Ardından, bir kaynak kodu dosyası ekler ve uygulamanızın kodunu girersiniz.

[Bir sorunla karşılaştım.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Kaynak kodu dosyası ekleme

1. **Solution Explorer'da**HelloWorld projesini seçin. Menü çubuğunda, Yeni **Öğe** **Ekle** iletişim kutusunu açmak için **Yeni**Öğe Ekle seçeneğini belirleyin.

1. Yeni **Öğe Ekle** iletişim kutusunda, zaten seçilmemişse **Yüklenilen'in** altındaki **Visual C++** öğesini seçin. Orta bölmede **C++ dosyasını (.cpp)** seçin. *HelloWorld.cpp* **adını** değiştirin. İletişim kutusunu kapatmak ve dosyayı oluşturmak için **Ekle'yi** seçin.

   ![HelloWorld.cpp için kaynak dosya ekleme](media/vscpp-add-new-item.gif "HelloWorld.cpp için kaynak dosya ekleme")

Visual studio yeni, boş bir kaynak kodu dosyası oluşturur ve kaynak kodunuzu girmeye hazır bir düzenleyici penceresinde açar.

[Bir sorunla karşılaştım.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Kaynak dosyaya kod ekleme

1. Bu kodu HelloWorld.cpp düzenleyici penceresine kopyalayın.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   Kod düzenleyici penceresinde aşağıdaki gibi görünmelidir:

   ![Merhaba Dünya kodu editör](media/vscpp-hello-world-editor.png "Merhaba Dünya kodu editör")

Kod editörde böyle göründüğünde, bir sonraki adıma geçmeye ve uygulamanızı oluşturmaya hazırsınız.

[Bir sorunla karşılaştım.](#add-a-source-code-file-issues)

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma ve çalıştırma](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

İlk C++ projenizi oluştururken sık karşılaşılan sorunların çözümleri için buraya gelin.

### <a name="create-your-app-project-issues"></a>Uygulama projenizi oluşturun: sorunlar

::: moniker range="vs-2019"

**Yeni Proje** iletişim kutusunda **C++** **,** Windows ve **Konsol** etiketleri olan bir **Konsol Uygulaması** şablonu gösterilmelidir. Eğer göremiyorsanız, iki olası nedeni vardır. Listeden filtrelenmiş olabilir veya yüklenmemiş olabilir. İlk olarak, şablonlar listesinin en üstündeki filtre açılır düşüşlerini kontrol edin. **Bunları C++**, **Windows**ve **Konsol**olarak ayarlayın. C++ **Konsol Uygulaması** şablonu görünmelidir; aksi takdirde, C++ iş **yüküne sahip Masaüstü geliştirme** yüklenmez.

**C++ ile Masaüstü geliştirmeyüklemek**için, yeni **proje** iletişim kutusundan yükleyiciyi çalıştırabilirsiniz. Yükleyiciyi başlatmak için şablon listesinin altındaki **daha fazla araç ve özellik** yükle bağlantısını seçin. Kullanıcı **Hesabı Denetimi** iletişim kutusu izin istiyorsa, **Evet'i**seçin. Yükleyicide, C++ iş yüküne **sahip Masaüstü geliştirmenin** denetlendiğinden emin olun. Ardından Visual Studio yüklemenizi güncelleştirmek için **Değiştir'i** seçin.

Aynı ada sahip başka bir proje zaten varsa, projeniz için başka bir ad seçin. Veya varolan projeyi silin ve yeniden deneyin. Varolan bir projeyi silmek için Dosya Gezgini'ndeki çözüm klasörünü *(helloworld.sln* dosyasını içeren klasör) silin.

[Geri dön.](#create-your-app-project)

::: moniker-end

::: moniker range="vs-2017"

Yeni **Proje** iletişim kutusunda **Yüklü**altında **Bir Görsel C++** girişi görünmüyorsa, Visual Studio kopyanızda büyük olasılıkla **C++** iş yükü yüklü masaüstü geliştirme sayılmamaktadır. Yükleyiciyi **Yeni Proje** iletişim kutusundan çalıştırabilirsiniz. Yükleyiciyi yeniden başlatmak için **Open Visual Studio Installer** bağlantısını seçin. Kullanıcı **Hesabı Denetimi** iletişim kutusu izin istiyorsa, **Evet'i**seçin. Gerekirse yükleyiciyi güncelleştirin. Yükleyicide, C++ iş **yüküne sahip Masaüstü geliştirmenin** denetlendiğinden emin olun ve Visual Studio yüklemenizi güncelleştirmek için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="<=vs-2017"

Aynı ada sahip başka bir proje zaten varsa, projeniz için başka bir ad seçin. Veya varolan projeyi silin ve yeniden deneyin. Varolan bir projeyi silmek için Dosya Gezgini'ndeki çözüm klasörünü *(helloworld.sln* dosyasını içeren klasör) silin.

[Geri dön.](#create-your-app-project)

### <a name="make-your-project-a-console-app-issues"></a>Projenizi bir konsol uygulaması yapın: sorunlar

**Yapılandırma Özellikleri**altında listelenen **Bağlayıcı'yı** görmüyorsanız, Özellik **Sayfaları** iletişim kutusunu kapatmak için **İptal'i** seçin. Yeniden denemeden önce **HelloWorld** projesinin **Solution Explorer'da** seçildiğinden emin olun. Solution Explorer'da **HelloWorld** çözümünü veya başka bir öğeyi **seçmeyin.**

Açılan alt etme denetimi, siz özelliği seçene kadar **Alt Sistem** özellik düzenle kutusunda görünmez. Seçmek için yap kutusunu tıklatın. Veya, **Alt Sistem** vurgulanana kadar iletişim denetimleri arasında geçiş yapmak için **Sekme** tuşuna basabilirsiniz. Açılır açma denetimini seçin veya açmak için **Alt+Down** tuşuna basın.

[Geri dön](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Kaynak kodu dosyası ekleme: sorunlar

Kaynak kod dosyasına farklı bir ad verirseniz sorun yok. Ancak, projenize aynı kodu içeren birden fazla dosya eklemeyin.

Üstbilgi dosyası gibi projenize yanlış dosya türünü eklediyseniz, dosyayı silin ve yeniden deneyin. Dosyayı silmek için **Solution Explorer'da**dosyayı seçin. Ardından **Sil** tuşuna basın.

[Geri dön.](#add-a-source-code-file)

### <a name="add-code-to-the-source-file-issues"></a>Kaynak dosyaya kod ekleme: sorunlar

Kaynak kodu dosya düzenleyicisi penceresini yanlışlıkla kapattıysanız, kolayca yeniden açabilirsiniz. Açmak **için, Solution Explorer** penceresinde HelloWorld.cpp'ye çift tıklayın.

Kaynak kod düzenleyicisinde herhangi bir şeyin altında kırmızı dalgalı hareketler görünüyorsa, kodunuzu yazım, noktalama ve büyük/küçük harf örneğine uygun olup olmadığını denetleyin. Büyük/küçük harf C++ kodunda önemlidir.

[Geri dön.](#add-code-to-the-source-file)

::: moniker-end

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

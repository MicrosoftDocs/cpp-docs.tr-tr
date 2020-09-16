---
title: C++ konsol uygulama projesi oluşturma
description: Visual Studio 'da Microsoft C++ kullanarak bir Merhaba Dünya konsol uygulaması oluşturun.
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 333bb6ce1f3ea0db6b07d70ddd60d4a4be337abd
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686515"
---
# <a name="create-a-c-console-app-project"></a>C++ konsol uygulama projesi oluşturma

C++ Programcı için olağan başlangıç noktası "Merhaba, Dünya!" komut satırında çalışan uygulama. Bu, Visual Studio 'da Bu adımda oluşturacağınız şeydir.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 'Yu, C++ iş yükünün bilgisayarınızda yüklü ve çalışır şekilde masaüstü geliştirme ile birlikte çalıştırın. Henüz yüklenmemişse, bkz. [Visual Studio 'Da C++ desteğini yükleme](vscpp-step-0-installation.md).

## <a name="create-your-app-project"></a>Uygulama projenizi oluşturma

Visual Studio, bir uygulamanın kodunu düzenlemek için *projeleri* ve projelerinizi düzenleme *çözümlerini* kullanır. Bir proje, uygulamalarınızı derlemek için kullanılan tüm seçenekleri, konfigürasyonları ve kuralları içerir. Tüm proje dosyaları ve tüm dış dosyalar arasındaki ilişkiyi yönetir. Uygulamanızı oluşturmak için önce yeni bir proje ve çözüm oluşturacaksınız.

::: moniker range=">=vs-2019"

1. Visual Studio 'da, **Yeni proje oluştur** iletişim kutusunu açmak için **Dosya** menüsünü açın ve **Yeni > proje** ' yi seçin. **C++**, **Windows**ve **konsol** etiketlerine sahip **konsol uygulaması** şablonunu seçin ve ardından **İleri**' yi seçin.

   ![Yeni bir proje oluşturma](media/vs2019-choose-console-app.png "Yeni proje oluştur iletişim kutusunu açın")

1. **Yeni projenizi yapılandırın** Iletişim kutusunda **Proje adı** düzenleme kutusuna *HelloWorld* yazın. Projeyi oluşturmak için **Oluştur** ' a tıklayın.

   ![Yeni projenizi yapılandırma iletişim kutusunun, proje adı metin alanına yazılan Merhaba Dünya ekran görüntüsü.](media/vs2019-configure-new-project-hello-world.png "Yeni projeyi adlandırın ve oluşturun")

   Visual Studio yeni bir proje oluşturur. Kaynak kodunuzu ekleme ve düzenleme için hazırız. Varsayılan olarak, konsol uygulama şablonu kaynak kodunuzu bir "Merhaba Dünya" uygulamasıyla doldurur:

   ![IDE 'de Merhaba Dünya Projesi](media/vs2019-hello-world-code.png "IDE 'de Merhaba Dünya Projesi")

   Kod düzenleyicide şuna benzer olduğunda, sonraki adıma geçmeye ve uygulamanızı oluşturmaya hazırsınız demektir.

[Bir sorunla karşılaştık.](#create-your-app-project-issues)

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio 'da **Dosya** menüsünü açın ve yeni **Proje** Iletişim kutusunu açmak için **Yeni > proje** ' yi seçin.

   ![Yeni proje iletişim kutusunu aç](media/vscpp-file-new-project.gif "Yeni proje iletişim kutusunu aç")

1. **Yeni proje** iletişim kutusunda, zaten seçili değilse **Visual C++ >** seçin ve **boş proje** şablonunu seçin. **Ad** alanına *HelloWorld*yazın. Projeyi oluşturmak için **Tamam ' ı** seçin.

   ![Yeni proje iletişim kutusunun yüklü > Visual C Plus Plus ile seçili ve çağrıldı, dışarı çağrılan boş proje seçeneği ve ad metin kutusuna yazılan Hellow dünya ekran görüntüsü.](media/vscpp-concierge-project-name-callouts.png "Yeni projeyi adlandırın ve oluşturun")

Visual Studio yeni, boş bir proje oluşturur. Oluşturmak istediğiniz uygulama türü için özelleştirme ve kaynak kod dosyalarınızı eklemek için size hazırlanın. Bundan sonra o işlemi yapacaksınız.

[Bir sorunla karşılaştık.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>Projenizi bir konsol uygulaması yapın

Visual Studio, Windows ve diğer platformlar için tüm uygulama ve bileşen türlerini oluşturabilir. **Boş proje** şablonu, oluşturduğu uygulama türü hakkında özel değildir. *Konsol uygulaması* , konsol veya komut istemi penceresinde çalıştırılan bir uygulamadır. Bir tane oluşturmak için, Visual Studio 'nun konsol alt sistemini kullanmak üzere uygulamanızı oluşturmasını söylemeniz gerekir.

1. Visual Studio 'da **Proje** menüsünü açın ve **Özellikler** ' i seçerek **HelloWorld Özellik sayfaları** iletişim kutusunu açın.

1. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri > bağlayıcı > sistem**' i seçin ve sonra **alt sistem** özelliğinin yanındaki düzenleme kutusunu seçin. Görüntülenen açılır menüde konsol ' ı **(/SUBSYSTEM: Console)** seçin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

   ![Özellik sayfaları iletişim kutusunu açın](media/vscpp-properties-linker-subsystem.gif "Özellik sayfaları iletişim kutusunu açın")

Visual Studio artık projenizi bir konsol penceresinde çalışacak şekilde derlemeyi biliyor. Ardından, bir kaynak kodu dosyası ekleyecek ve uygulamanız için kod girmeniz gerekir.

[Bir sorunla karşılaştık.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>Kaynak kodu dosyası Ekle

1. **Çözüm Gezgini**' de HelloWorld projesini seçin. **Yeni öğe Ekle** iletişim kutusunu açmak için menü çubuğunda **Proje**, **Yeni öğe Ekle** ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, zaten seçili değilse **yüklü** **Visual C++** seçin. Orta bölmede **C++ dosyası (. cpp)** öğesini seçin. **Adı** *HelloWorld. cpp*olarak değiştirin. İletişim kutusunu kapatmak ve dosyayı oluşturmak için **Ekle** ' yi seçin.

   ![HelloWorld. cpp için bir kaynak dosyası ekleyin](media/vscpp-add-new-item.gif "HelloWorld. cpp için bir kaynak dosyası ekleyin")

Visual Studio, yeni, boş bir kaynak kod dosyası oluşturur ve kaynak kodunuzu girmeye HAZIRAN bir düzenleyici penceresinde açar.

[Bir sorunla karşılaştık.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>Kaynak dosyaya kod ekleyin

1. Bu kodu HelloWorld. cpp düzenleyici penceresine kopyalayın.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   Kod, düzenleyici penceresinde şöyle görünmelidir:

   ![Düzenleyicide Merhaba Dünya kodu](media/vscpp-hello-world-editor.png "Düzenleyicide Merhaba Dünya kodu")

Kod düzenleyicide şuna benzer olduğunda, sonraki adıma geçmeye ve uygulamanızı oluşturmaya hazırsınız demektir.

[Bir sorunla karşılaştık.](#add-a-source-code-file-issues)

::: moniker-end

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [C++ projesi oluşturma ve çalıştırma](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>Sorun giderme kılavuzu

İlk C++ projenizi oluştururken sık karşılaşılan sorunların çözümleri için buraya gelin.

### <a name="create-your-app-project-issues"></a>Uygulama projenizi oluşturma: sorunlar

::: moniker range="vs-2019"

**Yeni proje** iletişim kutusunda **C++**, **Windows**ve **konsol** etiketleri bulunan bir **konsol uygulaması** şablonu gösterilmelidir. Bunu görmüyorsanız, iki olası neden vardır. Listenin dışına filtre uygulanabilir veya yüklenmemiş olabilir. İlk olarak, şablon listesinin en üstünde yer alarak filtre açılan listelerini denetleyin. Bunları **C++**, **Windows**ve **konsoluna**ayarlayın. C++ **konsol uygulaması** şablonu görünmelidir; Aksi halde, C++ iş yüküyle **masaüstü geliştirme** yüklü değildir.

**C++ Ile masaüstü geliştirme**yüklemek Için, **Yeni proje** iletişim kutusundan yükleyiciyi hemen çalıştırabilirsiniz. Yükleyiciyi başlatmak için şablon listesinin altındaki **daha fazla araç ve özellik yükleme** bağlantısını seçin. **Kullanıcı hesabı denetimi** iletişim kutusu izinleri Istediğinde, **Evet**' i seçin. Yükleyicide, C++ iş yüküyle **masaüstü geliştirme** 'nın işaretli olduğundan emin olun. Ardından, Visual Studio yüklemenizi güncelleştirmek için **Değiştir** ' i seçin.

Aynı ada sahip başka bir proje zaten varsa, projeniz için başka bir ad seçin. Veya mevcut projeyi silip yeniden deneyin. Mevcut bir projeyi silmek için dosya Gezgini 'ndeki çözüm klasörünü ( *HelloWorld. sln* dosyasını içeren klasör) silin.

[Geri dönün](#create-your-app-project).

::: moniker-end

::: moniker range="vs-2017"

**Yeni proje** iletişim kutusunda, **yüklü**' ın altında bir **Visual C++** girişi gösterilmezse, Visual Studio kopyanızın büyük olasılıkla C++ iş yükünün yüklü **olduğu masaüstü geliştirmesi** yoktur. **Yeni proje** iletişim kutusundan yükleyiciyi hemen çalıştırabilirsiniz. Yükleyiciyi yeniden başlatmak için **Visual Studio yükleyicisi aç** bağlantısını seçin. **Kullanıcı hesabı denetimi** iletişim kutusu izinleri Istediğinde, **Evet**' i seçin. Gerekirse yükleyiciyi güncelleştirin. Yükleyicide, C++ iş yükü **Ile masaüstü geliştirme** iş yükünün işaretli olduğundan emin olun ve Visual Studio yüklemenizi güncelleştirmek için **Tamam** ' ı seçin.

::: moniker-end

::: moniker range="<=vs-2017"

Aynı ada sahip başka bir proje zaten varsa, projeniz için başka bir ad seçin. Veya mevcut projeyi silip yeniden deneyin. Mevcut bir projeyi silmek için dosya Gezgini 'ndeki çözüm klasörünü ( *HelloWorld. sln* dosyasını içeren klasör) silin.

[Geri dönün](#create-your-app-project).

### <a name="make-your-project-a-console-app-issues"></a>Projenizi bir konsol uygulaması yapın: sorunlar

**Yapılandırma özellikleri**altında listelenmiş **bağlayıcı** görmüyorsanız, **Özellik sayfaları** iletişim kutusunu kapatmak için **iptal** ' i seçin. Yeniden denemeden önce **HelloWorld** projesinin **Çözüm Gezgini** seçildiğinden emin olun. **Çözüm Gezgini**' de **HelloWorld** çözümünü ya da başka bir öğeyi seçmeyin.

Özelliği seçinceye kadar, DropDown denetimi **alt sistem** özelliği düzenleme kutusunda görünmez. Düzenleme kutusuna tıklayarak seçin. Ya da **alt sistem** vurgulanana kadar iletişim kutusu denetimlerinde geçiş yapmak için **Tab** tuşuna basabilirsiniz. Açılır denetimi seçin veya açmak için **alt + aşağı** tuşlarına basın.

[Geri dön](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>Kaynak kodu dosyası ekleme: sorunlar

Kaynak kod dosyasına farklı bir ad vermeniz normaldir. Ancak, projenize aynı kodu içeren birden fazla dosya eklemeyin.

Projenize yanlış dosya türünü eklediyseniz (örneğin, bir üstbilgi dosyası), dosyayı silip yeniden deneyin. Dosyayı silmek için **Çözüm Gezgini**' de seçin. Ardından **Delete** tuşuna basın.

[Geri dönün](#add-a-source-code-file).

### <a name="add-code-to-the-source-file-issues"></a>Kaynak dosyaya kod ekleyin: sorunlar

Kaynak kodu dosya Düzenleyicisi penceresini yanlışlıkla kapattıysanız, tekrar kolayca açabilirsiniz. Açmak için **Çözüm Gezgini** penceresinde HelloWorld. cpp öğesine çift tıklayın.

Kırmızı dalgalı çizgiler, kaynak kodu düzenleyicisinde herhangi bir işlem altında görünürse, kodunuzun yazım, noktalama ve durumda örnekle eşleşip eşleşmediğini denetleyin. Örnek, C++ kodunda önemlidir.

[Geri dönün](#add-code-to-the-source-file).

::: moniker-end

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />

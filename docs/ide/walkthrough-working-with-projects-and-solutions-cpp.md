---
title: 'İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)'
ms.date: 05/14/2019
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
ms.openlocfilehash: 36c64a74310c72df38021aebd8abb3ee430da3f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375889"
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)

Visual Studio'da nasıl C++ projesi oluşturulduğu, nasıl kod eklendiği ve ardından projenin nasıl oluşturulup çalıştırıldığını burada bulabilirsiniz. Bu adım adım öğreticideki proje, kaç oyuncunun farklı kart oyunları oynadığını izleyen bir programdır.

Visual Studio'da projeler ve çözümler de yer almaktadır. Bir çözüm birden fazla proje olabilir-örneğin, bir DLL ve bir yürütülebilir bu DLL başvurur. Daha fazla bilgi için [Çözümler ve Projeler'e](/visualstudio/ide/solutions-and-projects-in-visual-studio)bakın.

## <a name="before-you-start"></a>Başlamadan önce

Bu gözden geçirme yi tamamlamak için Visual Studio 2017 veya daha sonra sınamalısınız. Bir kopyaya ihtiyacınız varsa, burada kısa bir kılavuz: [Visual Studio C++ desteği yükleyin.](../build/vscpp-step-0-installation.md) Henüz yapmadıysanız, C++ bileşenlerinin doğru şekilde yüklendiğinden ve her şeyin çalıştığından emin olmak için "Hello, World" öğreticisi aracılığıyla yüklemeden sonraki adımları izleyin.

C++ dilinin temellerini anlamak ve derleyici, bağlayıcı ve hata ayıklayıcının ne için kullanıldığını bilmek yardımcı olur. Öğretici ayrıca Windows'u bildiğinizi ve menüleri, iletişim leri nasıl kullanacağınızı da varsayar,

## <a name="create-a-project"></a>Proje oluşturma

Proje oluşturmak için önce bir proje türü şablonu seçin. Her proje türü için Visual Studio derleyici ayarlarını ayarlar ve türüne bağlı olarak daha sonra değiştirebileceğiniz başlangıç kodu oluşturur. Aşağıdaki adımlar Visual Studio'nun hangi sürümünü kullandığınıza bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-project-in-visual-studio-2019"></a>Visual Studio 2019'da proje oluşturmak için

1. Ana menüden, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **Konsol'a**ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Konsol Uygulaması'nı** seçin ve **ardından İleri'yi**seçin. Bir sonraki sayfada, projenin adı olarak *Oyunu* girin.

   **Konum** açılır listesindevarsayılan konumu kabul edebilir, farklı bir konum girebilir veya projeyi kaydetmek istediğiniz bir dizine göz atmak için **Gözat** düğmesini seçebilirsiniz.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözüme koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. **Çözüm adı** kutusundaki adı değiştirebilirsiniz, ancak bu örnekte varsayılan adı saklayabilirsiniz.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

   Visual Studio yeni çözüm ve proje dosyalarınızı oluşturur ve oluşturduğu Game.cpp kaynak kodu dosyasının düzenleyicisini açar.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017"></a>Visual Studio 2017'de proje oluşturmak için

1. Menü çubuğunda **Yeni** > **Proje** **yi seçin.** >

1. **Yeni Proje** iletişim kutusunun sol bölmesinde, **Yüklenilen'i** genişletin ve zaten açık değilse **Visual C++'ı**seçin.

1. Orta bölmedeki yüklü şablonlar listesinde **Windows Console Uygulaması'nı**seçin.

1. **Ad** kutusuna proje için bir ad girin. Bu örnekiçin, *Oyunu*girin.

   **Konum** açılır listesindevarsayılan konumu kabul edebilir, farklı bir konum girebilir veya projeyi kaydetmek istediğiniz bir dizine göz atmak için **Gözat** düğmesini seçebilirsiniz.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözüme koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. **Çözüm adı** kutusundaki adı değiştirebilirsiniz, ancak bu örnekte varsayılan adı saklayabilirsiniz.

1. Projeyi oluşturmak için **Tamam** düğmesini seçin.

   Visual Studio yeni çözüm ve proje dosyalarınızı oluşturur ve oluşturduğu Game.cpp kaynak kodu dosyasının düzenleyicisini açar.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-project-in-visual-studio-2015"></a>Visual Studio 2015'te bir proje oluşturmak için

1. Menü çubuğunda **Yeni** > **Proje** **yi seçin.** >

1. **Yeni Proje** iletişim kutusunun sol bölmesinde, **Yüklenilen'i** genişletin ve zaten açık değilse **Visual C++'ı**seçin.

1. Orta bölmedeki yüklü şablonlar listesinde **Win32 Konsol Uygulaması'nı**seçin.

1. **Ad** kutusuna proje için bir ad girin. Bu örnekiçin, *Oyunu*girin.

   **Konum** açılır listesindevarsayılan konumu kabul edebilir, farklı bir konum girebilir veya projeyi kaydetmek istediğiniz bir dizine göz atmak için **Gözat** düğmesini seçebilirsiniz.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözüme koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. **Çözüm adı** kutusundaki adı değiştirebilirsiniz, ancak bu örnekte varsayılan adı saklayabilirsiniz.

1. Projeyi oluşturmak için **Tamam** düğmesini seçin.

   Visual Studio yeni çözüm ve proje dosyalarınızı oluşturur ve oluşturduğu Game.cpp kaynak kodu dosyasının düzenleyicisini açar.

::: moniker-end

## <a name="organize-projects-and-files"></a>Projeleri ve dosyaları düzenleme

**Çözümdeki** projeleri, dosyaları ve diğer kaynakları düzenlemek ve yönetmek için Solution Explorer'ı kullanabilirsiniz.

Gözden geçirme nin bu bölümü projeye nasıl sınıf ekleyeceğini gösterir. Sınıfı eklediğinizde, Visual Studio karşılık gelen .h ve .cpp dosyalarını ekler. **Sonuçları Çözüm Gezgini'nde**görebilirsiniz.

### <a name="to-add-a-class-to-a-project"></a>Bir projeye sınıf eklemek için

1. Çözüm **Gezgini** penceresi Visual Studio'da, menü çubuğunda görüntülenmiyorsa,**Çözüm Gezgini** **Görüntüle'yi** > seçin.

1. **Solution Explorer'da** **Oyun** projesini seçin. Menü çubuğunda, **Sınıf Ekle'yi** > **Add Class**seçin.

1. Sınıf **Ekle** iletişim kutusunda, **Sınıf Adı** kutusuna *Cardgame'i* girin. Varsayılan dosya adlarını ve ayarlarını değiştirmeyin. **Tamam** düğmesini seçin.

   Visual Studio yeni dosyalar oluşturur ve bunları projenize ekler. **Bunları Çözüm Gezgini** penceresinde görebilirsiniz. Cardgame.h ve Cardgame.cpp dosyaları editörde açılır.

1. Cardgame.h dosyasını edin ve şu değişiklikleri yapın:

   - Sınıf tanımının açılış ayracından sonra iki özel veri üyesi ekleyin.
     <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio'nun ürettiği varsayılan oluşturucuyu değiştirin. Erişim `public:` belirticiden sonra aşağıdaki gibi görünen satırı bulun:

      `Cardgame();`

      Bir tür parametre almak için `int`yapıcı değiştirin , *adlı oyuncular*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - Varsayılan yıkıcıdan sonra, *GetParticipants* adlı bir üye işlev için hiçbir parametre almayan `totalParticipants` ve değeri döndüren satır `static int` başı bir bildirim ekleyin.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   Cardgame.h dosyası, siz değiştirdikten sonra aşağıdaki koda benzemelidir:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]-->

    ```cpp
    #pragma once
    class Cardgame
    {
        int players;
        static int totalParticipants;
    public:
        Cardgame(int players);
        ~Cardgame();
        static int GetParticipants() { return totalParticipants; }
    };
    ```

   Satır `#pragma once` derleyiciye üstbilgi dosyasını yalnızca bir kez eklemesini söyler. Daha fazla bilgi için [bir kez](../preprocessor/once.md)bakın. Yukarıdaki başlık dosyasındaki diğer C++ anahtar kelimeleri hakkında [int](../cpp/fundamental-types-cpp.md)bilgi [static](../cpp/storage-classes-cpp.md)için [bkz.](../cpp/class-cpp.md) [public](../cpp/public-cpp.md)

1. Düzenleme için açmak için düzenleme bölmesinin üst kısmındaki **Cardgame.cpp** sekmesini seçin.

1. Dosyadaki her şeyi silin ve kodla değiştirin:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->

    ```cpp
    #include "pch.h" // remove this line in Visual Studio 2019
    #include "Cardgame.h"
    #include <iostream>

    using namespace std;

    int Cardgame::totalParticipants = 0;

    Cardgame::Cardgame(int players)
        : players(players)
    {
        totalParticipants += players;
        cout << players << " players have started a new game.  There are now "
             << totalParticipants << " players in total." << endl;
    }

    Cardgame::~Cardgame()
    {
    }
    ```

   > [!NOTE]
   > Kod girerken otomatik tamamlamayı kullanabilirsiniz. Örneğin, bu kodu klavyeye girerseniz pl *veya* *tot'u* girip **Ctrl**+**Spacebar**tuşuna basabilirsiniz. Otomatik tamamlama `players` girer `totalParticipants` veya sizin için.

## <a name="add-test-code-to-your-main-function"></a>Ana işlevinize test kodu ekleme

Uygulamanıza yeni işlevleri sınayen bazı kodlar ekleyin.

### <a name="to-add-test-code-to-the-project"></a>Projeye test kodu eklemek için

1. **Game.cpp** düzenleyici penceresinde, varolan kodu aşağıdakilerle değiştirin:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->

    ```cpp
    // Game.cpp : Defines the entry point for the console application.
    //

    #include "pch.h" // remove this line in Visual Studio 2019
    #include "Cardgame.h"
    #include <iostream>

    using namespace std;

    void PlayGames()
    {
        Cardgame bridge(4);
        Cardgame blackjack(8);
        Cardgame solitaire(1);
        Cardgame poker(5);
    }

    int main()
    {
        PlayGames();
        return 0;
    }
    ```

   Kod, `PlayGames`kaynak koduna bir test işlevi ekler ve `main`onu .

## <a name="build-and-run-your-app-project"></a>Uygulama projenizi oluşturun ve çalıştırın

Ardından, projeyi oluşturun ve uygulamayı çalıştırın.

### <a name="to-build-and-run-the-project"></a>Projeyi derleyip çalıştırmak için

1. Menü çubuğunda **Yapı** > **Çözüm'üne**bakın.

   Yapının çıktısı **Çıktı** penceresinde görüntülenir. Yapınız başarılı olursa, çıktı aşağıdakilere benzemelidir:

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>pch.cpp
    1>Cardgame.cpp
    1>Game.cpp
    1>Generating Code...
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

   **Çıktı** penceresi, yapı yapılandırmasıbağlı olarak farklı adımlar gösterebilir, ancak proje yapısı başarılı olursa, son satır gösterilen çıktıya benzemelidir.

   Yapınız başarılı olmadıysa, kodunuzu önceki adımlarda gösterilen kodla karşılaştırın.

1. Projeyi çalıştırmak için menü çubuğunda Hata**Ayıklama Başlatma'yı** **seçin.** >  Bir konsol penceresi görünmeli ve çıktı benzer olmalıdır:

    ```Output
    4 players have started a new game.  There are now 4 players in total.
    8 players have started a new game.  There are now 12 players in total.
    1 players have started a new game.  There are now 13 players in total.
    5 players have started a new game.  There are now 18 players in total.
    ```

   Konsol penceresini kapatmak için bir tuşa basın.

Tebrikler, başarılı bir uygulama projesi ve çözüm inşa ettik. Visual Studio'da C++ kod projelerinin nasıl oluşturulabildiğini öğrenmek için izliğe devam edin.

## <a name="next-steps"></a>Sonraki adımlar

**Önceki:** [C++ Masaüstü Geliştirme için Visual Studio IDE'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)<br/>
**Sonraki:** [Walkthrough: Proje Oluşturma (C++)](../ide/walkthrough-building-a-project-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[Projeler ve yapı sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

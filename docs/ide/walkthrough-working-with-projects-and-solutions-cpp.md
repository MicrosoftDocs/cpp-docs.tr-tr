---
title: 'İzlenecek yol: Projeler ve çözümler (C++) ile çalışma'
ms.date: 04/25/2019
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
ms.openlocfilehash: 978899e6e73d78623e37222e3248dc299ec29c69
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877298"
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>İzlenecek yol: Projeler ve çözümler (C++) ile çalışma

Visual Studio'da nasıl C++ projesi oluşturulduğu, nasıl kod eklendiği ve ardından projenin nasıl oluşturulup çalıştırıldığını burada bulabilirsiniz. Bu adım adım öğreticideki proje, kaç oyuncunun farklı kart oyunları oynadığını izleyen bir programdır.

Visual Studio'da iş, projeler ve çözümler halinde düzenlenmiştir. Bir çözüm birden fazla proje olabilir — örneğin, bir DLL ve bu DLL'ye başvuran yürütülebilir bir dosya. Daha fazla bilgi için [çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="before-you-start"></a>Başlamadan önce

Bu izlenecek yolu tamamlamak için Visual Studio 2017 veya üstü gerekir. Bir kopyası gerekirse, kısa bir kılavuz aşağıda verilmiştir: [Visual Studio'da C++ desteği yükleme](../build/vscpp-step-0-installation.md). Bunu henüz yapmadıysanız sonraki adımları aracılığıyla Visual C++'ın doğru şekilde yüklendiğinden emin olmak için "Hello, World" öğretici ve yüklemeden sonra tüm works izleyin.

C++ dilinin temellerini anlamanız ve bildiğiniz ne derleyici, bağlayıcı ve hata ayıklayıcı için kullanılan yardımcı olur. Öğreticide ayrıca Windows ve menüler, iletişim kutuları kullanma ile ilgili bilgi sahibi olduğunuz varsayılır,

## <a name="create-a-project"></a>Proje oluşturma

Proje oluşturmak için önce bir proje türü şablonu seçin. Her proje türü için Visual Studio derleyici ayarlarını belirler ve — türüne bağlı olarak — daha sonra değiştirebileceğiniz Başlatıcı kodu üretir. Aşağıdaki adımlar, kullandığınız Visual Studio'nun hangi sürümünün bağlı olarak farklılık gösterir. Sol üst sürüm seçicisinde doğru sürüme bu sayfanın ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-project-in-visual-studio-2019"></a>Visual Studio 2019 içinde bir proje oluşturmak için

1. Ana menüden **dosya** > **yeni** > **proje** açmak için **yeni bir proje oluşturma** iletişim bir kutu.

1. İletişim kutusunun üstündeki ayarlamak **dil** için **C++** ayarlayın **Platform** için **Windows**, ayarlayıp **proje türü** için **konsol**. 

1. Filtrelenmiş proje türleri listesinden seçim **konsol uygulaması** ardından **sonraki**. Sonraki sayfaya girin *Game* projenin adı.

   Varsayılan konumu kabul edebilir **konumu** açılır listede farklı bir konum girin veya seçin **Gözat** , projeyi kaydetmek istediğiniz dizine gitmek için düğme.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözümün içine koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. Adı değiştirebilirsiniz **çözüm adı** kutusu, ancak bu örnekte, varsayılan adı bırakın.

1. Seçin **Oluştur** projeyi oluşturmak için.

   Visual Studio, yeni çözüm ve proje dosyalarını oluşturur ve onu oluşturulmuş Game.cpp kaynak kodu dosyası düzenleyicisi açılır.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017"></a>Visual Studio 2017'de bir proje oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** seçip **Visual C++**, zaten açık değilse.

1. Orta bölmedeki yüklü şablonlar listesinde seçin **Windows konsol uygulaması**.

1. Proje için bir ad girin **adı** kutusu. Bu örnekte, girin *Game*.

   Varsayılan konumu kabul edebilir **konumu** açılır listede farklı bir konum girin veya seçin **Gözat** , projeyi kaydetmek istediğiniz dizine gitmek için düğme.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözümün içine koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. Adı değiştirebilirsiniz **çözüm adı** kutusu, ancak bu örnekte, varsayılan adı bırakın.

1. Seçin **Tamam** projeyi oluşturmak için.

   Visual Studio, yeni çözüm ve proje dosyalarını oluşturur ve onu oluşturulmuş Game.cpp kaynak kodu dosyası düzenleyicisi açılır.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-project-in-visual-studio-2015"></a>Visual Studio 2015'te bir proje oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** seçip **Visual C++**, zaten açık değilse.

1. Orta bölmedeki yüklü şablonlar listesinde seçin **Win32 konsol uygulaması**.

1. Proje için bir ad girin **adı** kutusu. Bu örnekte, girin *Game*.

   Varsayılan konumu kabul edebilir **konumu** açılır listede farklı bir konum girin veya seçin **Gözat** , projeyi kaydetmek istediğiniz dizine gitmek için düğme.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözümün içine koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. Adı değiştirebilirsiniz **çözüm adı** kutusu, ancak bu örnekte, varsayılan adı bırakın.

1. Seçin **Tamam** projeyi oluşturmak için.

   Visual Studio, yeni çözüm ve proje dosyalarını oluşturur ve onu oluşturulmuş Game.cpp kaynak kodu dosyası düzenleyicisi açılır.

::: moniker-end

## <a name="organize-projects-and-files"></a>Projeleri ve dosyaları düzenleme

Kullanabileceğiniz **Çözüm Gezgini** projeleri, dosyaları ve çözümünüzdeki diğer kaynakları düzenlemek ve yönetmek için.

Kılavuzun bu bölümü, projeye bir sınıf eklemek gösterilmektedir. Sınıfı eklediğinizde, Visual Studio karşılık gelen .h ve .cpp dosyaları ekler. Sonuçlarda gördüğünüz **Çözüm Gezgini**.

### <a name="to-add-a-class-to-a-project"></a>Bir projeye sınıf eklemek için

1. Varsa **Çözüm Gezgini** penceresi Visual Studio'da, menü çubuğundaki görüntülenmiyorsa öğesini **görünümü** > **Çözüm Gezgini**.

1. İçinde **Çözüm Gezgini**seçin **Game** proje. Menü çubuğunda, **proje** > **sınıfı Ekle**.

1. İçinde **sınıfı Ekle** iletişim kutusunda girin *Cardgame* içinde **sınıf adı** kutusu. Varsayılan dosya adlarını ve ayarlarını değiştirmeyin. Seçin **Tamam** düğmesi.

   Visual Studio, yeni dosyalar oluşturur ve bunları projenize ekler. Bunları gördüğünüz **Çözüm Gezgini** penceresi. Cardgame.h ve Cardgame.cpp dosyaları düzenleyicide açılır.

1. Cardgame.h dosyası düzenleyin ve şu değişiklikleri yapın:

   - Sınıf tanımının açılış ayracından sonra iki özel veri üyesi ekleyin.
     <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio'nun ürettiği varsayılan oluşturucuyu değiştirin. Sonra `public:` erişim belirticisi, şuna benzer satırı bulun:

      `Cardgame();`

      Türünden bir parametre için bir oluşturucuyu değiştirin `int`, adlandırılmış *oyuncuların*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - Varsayılan yıkıcıdan sonra eklemek için bir satır içi bildirim bir `static int` adlı üye işlevi *GetParticipants* , herhangi bir parametre alır ve döndürür `totalParticipants` değeri.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   Cardgame.h dosyası, siz değiştirdikten sonra aşağıdaki kodu benzemelidir:

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

   Satır `#pragma once` derleyici üstbilgi dosyası yalnızca bir kez dahil etmesini söyler. Daha fazla bilgi için [sonra](../preprocessor/once.md). Yukarıdaki üstbilgi dosyasındaki diğer C++ anahtar sözcükleri hakkında daha fazla bilgi için bkz. [sınıfı](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [statik](../cpp/storage-classes-cpp.md), ve [genel](../cpp/public-cpp.md).

1. Seçin **Cardgame.cpp** düzenlemek üzere açmak için düzenleme bölmesinin üst sekmesi.

1. Dosyadaki her şeyi silin ve kod ile değiştirin:

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
   > Kod girerken otomatik tamamlamayı kullanabilirsiniz. Klavye bu kodu girerseniz, örneğin, girebilirsiniz *pl* veya *tot* ve tuşuna **Ctrl**+**boşluk**. Otomatik Tamamlama girer `players` veya `totalParticipants` sizin için.

## <a name="add-test-code-to-your-main-function"></a>Test kodu ana işlevinize ekleyin

Yeni işlevleri test uygulamanıza kod ekleyin.

### <a name="to-add-test-code-to-the-project"></a>Test kodu projeye eklemek için

1. İçinde **Game.cpp** Düzenleyicisi penceresinde, varolan kod ile değiştirin:

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

   Kod bir test işlevi ekler `PlayGames`kaynak kodu ve çağrı içinde `main`.

## <a name="build-and-run-your-app-project"></a>Derleme ve uygulama projenizi çalıştırma

Ardından, projeyi oluşturun ve uygulamayı çalıştırın.

### <a name="to-build-and-run-the-project"></a>Projeyi derleyip çalıştırmak için

1. Menü çubuğunda, **derleme** > **Çözümü Derle**.

   Bir derlemenin çıktısı görüntülenir **çıkış** penceresi. Derlemeniz başarılıysa çıktı benzemelidir:

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>pch.cpp
    1>Cardgame.cpp
    1>Game.cpp
    1>Generating Code...
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

   **Çıkış** penceresi derleme yapılandırmasına bağlı olarak farklı adımlar gösterebilir, ancak proje derlemesi başarılı olursa son satır gösterilen çıktıya benzemelidir.

   Derlemeniz başarılı olmadıysa, kodunuzu önceki adımlarda gösterilen koda karşılaştırın.

1. Menü çubuğunda projeyi çalıştırmak için seçin **hata ayıklama** > **hata ayıklama olmadan Başlat**. Bir konsol penceresi görünür olmalıdır ve çıktıya benzemelidir:

    ```Output
    4 players have started a new game.  There are now 4 players in total.
    8 players have started a new game.  There are now 12 players in total.
    1 players have started a new game.  There are now 13 players in total.
    5 players have started a new game.  There are now 18 players in total.
    ```

   Konsol penceresini kapatmak için bir tuşa basın.

Tebrikler, bir uygulama projesi ve çözümü başarıyla derlediyseniz. İzlenecek yol, C++ kod projeleri Visual Studio'da derleme hakkında daha fazla bilgi için devam edin.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [C++ Masaüstü Geliştirmesi için Visual Studio IDE Kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)<br/>
**Sonraki:** [İzlenecek yol: Proje Derleme (C++)](../ide/walkthrough-building-a-project-cpp.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

---
description: 'Daha fazla bilgi edinin: Izlenecek yol: projelerle ve çözümlerle çalışma (C++)'
title: 'İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)'
ms.date: 05/14/2019
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
ms.openlocfilehash: f96c531a7a47e961b7e7da15ad455e3feefc6925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345283"
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)

Visual Studio'da nasıl C++ projesi oluşturulduğu, nasıl kod eklendiği ve ardından projenin nasıl oluşturulup çalıştırıldığını burada bulabilirsiniz. Bu adım adım öğreticideki proje, kaç oyuncunun farklı kart oyunları oynadığını izleyen bir programdır.

Visual Studio 'da iş, projelerde ve çözümlerde düzenlenmiştir. Bir çözüm birden fazla projeye sahip olabilir — Örneğin, bir DLL ve bu DLL 'ye başvuran yürütülebilir bir dosya. Daha fazla bilgi için bkz. [çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="before-you-start"></a>Başlamadan önce

Bu izlenecek yolu tamamlamak için Visual Studio 2017 veya sonraki bir sürümü gerekir. Bir kopyaya ihtiyacınız varsa, kısa bir kılavuz aşağıda verilmiştir: [Visual Studio 'Da C++ desteğini yükleyebilirsiniz](../build/vscpp-step-0-installation.md). Henüz yapmadıysanız, C++ bileşenlerinin doğru yüklendiğinden ve tümünün çalıştığından emin olmak için "Merhaba, Dünya" öğreticisi aracılığıyla yüklemeden sonraki adımları izleyin.

C++ dilinin temellerini anladıysanız ve derleyicilerin, bağlayıcının ve hata ayıklayıcının ne için kullanıldığını bildiğiniz konusunda yardımcı olur. Öğretici ayrıca Windows hakkında bilgi sahibi olduğunuzu ve menülerin, iletişim kutularının nasıl kullanılacağını varsayar.

## <a name="create-a-project"></a>Proje oluşturma

Proje oluşturmak için önce bir proje türü şablonu seçin. Her proje türü için, Visual Studio derleyici ayarlarını belirler ve türüne bağlı olarak, daha sonra değiştirebileceğiniz başlatıcı kodu oluşturur. Aşağıdaki adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="msvc-160"

### <a name="to-create-a-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir proje oluşturmak için

1.  >  > **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında,  **dili** **C++** olarak ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol** olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, proje için ad olarak *oyun* girin.

   **Konum** açılır listesinde varsayılan konumu kabul edebilir, farklı bir konum girebilir veya projeyi kaydetmek istediğiniz dizine gitmek Için, **tarayıcı** düğmesini seçebilirsiniz.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözüme koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. **Çözüm adı** kutusundaki adı değiştirebilirsiniz, ancak bu örnek için varsayılan adı saklayın.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

   Visual Studio yeni çözümünüzü ve proje dosyalarını oluşturur ve oluşturduğu Game. cpp kaynak kodu dosyası için düzenleyiciyi açar.

::: moniker-end

::: moniker range="msvc-150"

### <a name="to-create-a-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir proje oluşturmak için

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** ' ı genişletin ve açık değilse **Visual C++**' yi seçin.

1. Orta bölmedeki yüklü şablonlar listesinde, **Windows konsol uygulaması**' nı seçin.

1. **Ad** kutusuna proje için bir ad girin. Bu örnek için *oyun* girin.

   **Konum** açılır listesinde varsayılan konumu kabul edebilir, farklı bir konum girebilir veya projeyi kaydetmek istediğiniz dizine gitmek Için, **tarayıcı** düğmesini seçebilirsiniz.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözüme koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. **Çözüm adı** kutusundaki adı değiştirebilirsiniz, ancak bu örnek için varsayılan adı saklayın.

1. Projeyi oluşturmak için **Tamam** düğmesini seçin.

   Visual Studio yeni çözümünüzü ve proje dosyalarını oluşturur ve oluşturduğu Game. cpp kaynak kodu dosyası için düzenleyiciyi açar.

::: moniker-end

::: moniker range="msvc-140"

### <a name="to-create-a-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de bir proje oluşturmak için

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** ' ı genişletin ve açık değilse **Visual C++**' yi seçin.

1. Orta bölmedeki yüklü şablonlar listesinde **Win32 konsol uygulaması**' nı seçin.

1. **Ad** kutusuna proje için bir ad girin. Bu örnek için *oyun* girin.

   **Konum** açılır listesinde varsayılan konumu kabul edebilir, farklı bir konum girebilir veya projeyi kaydetmek istediğiniz dizine gitmek Için, **tarayıcı** düğmesini seçebilirsiniz.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözüme koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. **Çözüm adı** kutusundaki adı değiştirebilirsiniz, ancak bu örnek için varsayılan adı saklayın.

1. Projeyi oluşturmak için **Tamam** düğmesini seçin.

   Visual Studio yeni çözümünüzü ve proje dosyalarını oluşturur ve oluşturduğu Game. cpp kaynak kodu dosyası için düzenleyiciyi açar.

::: moniker-end

## <a name="organize-projects-and-files"></a>Projeleri ve dosyaları düzenleme

Çözümünüzde projeleri, dosyaları ve diğer kaynakları düzenlemek ve yönetmek için **Çözüm Gezgini** kullanabilirsiniz.

İzlenecek yolun bu bölümü, projeye bir sınıfın nasıl ekleneceğini gösterir. Sınıfı eklediğinizde, Visual Studio karşılık gelen. h ve. cpp dosyalarını ekler. Sonuçları **Çözüm Gezgini** görebilirsiniz.

### <a name="to-add-a-class-to-a-project"></a>Bir projeye sınıf eklemek için

1. **Çözüm Gezgini** penceresi Visual Studio 'da görüntülenmiyorsa, menü çubuğunda, Çözüm Gezgini **görüntüle**' yi seçin  >  .

1. **Çözüm Gezgini**, **oyun** projesini seçin. Menü çubuğunda **Proje**  >  **sınıfı Ekle**' yi seçin.

1. **Sınıf Ekle** iletişim kutusunda, **sınıf adı** kutusuna *Cardgame* yazın. Varsayılan dosya adlarını ve ayarlarını değiştirmeyin. **Tamam** düğmesini seçin.

   Visual Studio yeni dosyalar oluşturup projenize ekler. Bunları **Çözüm Gezgini** penceresinde görebilirsiniz. Cardgame. h ve Cardgame. cpp dosyaları düzenleyicide açılır.

1. Cardgame. h dosyasını düzenleyin ve şu değişiklikleri yapın:

   - Sınıf tanımının açılış ayracından sonra iki özel veri üyesi ekleyin.
     <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio'nun ürettiği varsayılan oluşturucuyu değiştirin. `public:`Erişim belirticisinden sonra şöyle görünen satırı bulun:

      `Cardgame();`

      Oluşturucuyu **`int`** , *oynatıcı adlı oyuncu* türünde bir parametre alacak şekilde değiştirin.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - Varsayılan yıkıcıdan sonra, `static int` hiçbir parametre alan ve değeri döndüren *getkatılımcılar* adlı bir üye işlevi için bir satır içi bildirim ekleyin `totalParticipants` .

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   Cardgame. h dosyası, değiştirdikten sonra aşağıdaki koda benzemelidir:

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

   Çizgi `#pragma once` , derleyiciye başlık dosyasını yalnızca bir kez eklemesini söyler. Daha fazla bilgi için bkz. [bir kez](../preprocessor/once.md). Yukarıdaki üstbilgi dosyasındaki diğer C++ anahtar sözcükleri hakkında daha fazla bilgi için bkz. [Class](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [static](../cpp/storage-classes-cpp.md)ve [Public](../cpp/public-cpp.md).

1. Düzenlenmek üzere açmak için, düzen bölmesinin en üstündeki **Cardgame. cpp** sekmesini seçin.

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
   > Kod girerken otomatik tamamlamayı kullanabilirsiniz. Örneğin, bu kodu klavyeye girerseniz, *pl* veya *Sigortalanan top* girebilir ve ardından **CTRL** + **boşluk** tuşlarına basabilirsiniz. Otomatik Tamamlama `players` `totalParticipants` sizin için veya sizin için girer.

## <a name="add-test-code-to-your-main-function"></a>Ana işlevinizde test kodu ekleyin

Uygulamanıza yeni işlevleri test eden bazı kodlar ekleyin.

### <a name="to-add-test-code-to-the-project"></a>Projeye test kodu eklemek için

1. **Game. cpp** düzenleyici penceresinde, var olan kodu şu şekilde değiştirin:

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

   Kod, kaynak koda bir test işlevi ekler `PlayGames` ve bunu içinde çağırır `main` .

## <a name="build-and-run-your-app-project"></a>Uygulama projenizi derleyin ve çalıştırın

Sonra, projeyi derleyin ve uygulamayı çalıştırın.

### <a name="to-build-and-run-the-project"></a>Projeyi derleyip çalıştırmak için

1. Menü **çubuğunda Build**  >  **Build Solution** öğesini seçin.

   Bir **derlemeden çıkış çıkış penceresinde görüntülenir** . Derlemeniz başarılı olursa çıkışın aşağıdakine benzer olması gerekir:

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>pch.cpp
    1>Cardgame.cpp
    1>Game.cpp
    1>Generating Code...
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

   **Çıkış** penceresi, derleme yapılandırmasına bağlı olarak farklı adımlar gösterebilir, ancak proje derlemesi başarılı olursa, son satır gösterilen çıktıya benzemelidir.

   Derlemeniz başarılı olmadıysa, kodunuzu önceki adımlarda gösterilen kodla karşılaştırın.

1. Projeyi çalıştırmak için menü çubuğunda **hata ayıklama**  >  **başlatma hatası olmadan Başlat**' ı seçin. Bir konsol penceresi görünmelidir ve çıktının şöyle olması gerekir:

    ```Output
    4 players have started a new game.  There are now 4 players in total.
    8 players have started a new game.  There are now 12 players in total.
    1 players have started a new game.  There are now 13 players in total.
    5 players have started a new game.  There are now 18 players in total.
    ```

   Konsol penceresini kapatmak için bir tuşa basın.

Tebrikler, bir uygulama projesini ve çözümünü başarıyla oluşturdunuz. Visual Studio 'da C++ kod projeleri oluşturma hakkında daha fazla bilgi edinmek için İzlenecek yol ile devam edin.

## <a name="next-steps"></a>Sonraki adımlar

**Önceki:** [C++ masaüstü geliştirme IÇIN Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)<br/>
**İleri:** [Izlenecek yol: proje derleme (C++)](../ide/walkthrough-building-a-project-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

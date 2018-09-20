---
title: 'İzlenecek yol: Projeler ve çözümler (C++) ile çalışma | Microsoft Docs'
ms.custom: ''
ms.date: 09/14/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abd65d209bf24fb9285937cc998bd82d5ef3cb4f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418170"
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)

Visual Studio'da nasıl C++ projesi oluşturulduğu, nasıl kod eklendiği ve ardından projenin nasıl oluşturulup çalıştırıldığını burada bulabilirsiniz. Bu adım adım öğreticideki proje, kaç oyuncunun farklı kart oyunları oynadığını izleyen bir programdır.

Visual Studio'da iş, projeler ve çözümler halinde düzenlenmiştir. Bir çözüm birden fazla proje içerebilir; örneğin bir DLL ve bu DLL'ye başvuran yürütülebilir bir dosya. Daha fazla bilgi için [çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="before-you-start"></a>Başlamadan önce

Bu izlenecek yolu tamamlamak için Visual Studio 2017 sürüm 15.3 veya üzeri gerekir. Bir kopyası gerekirse, kısa bir kılavuz şöyledir: [Visual Studio'da C++ yükleme desteği](../build/vscpp-step-0-installation.md). Bunu henüz yapmadıysanız sonraki adımları aracılığıyla Visual C++'ın doğru şekilde yüklendiğinden emin olmak için "Hello, World" öğretici ve yüklemeden sonra tüm works izleyin.

C++ dilinin temellerini anlamanız ve bildiğiniz ne derleyici, bağlayıcı ve hata ayıklayıcı için kullanılan yardımcı olur. Öğreticide ayrıca Windows ve menüler, iletişim kutuları kullanma ile ilgili bilgi sahibi olduğunuz varsayılır,

## <a name="create-a-project"></a>Proje oluşturma

Proje oluşturmak için önce bir proje türü şablonu seçin. Her proje türü için Visual Studio derleyici ayarlarını belirler ve — türüne bağlı olarak — daha sonra değiştirebileceğiniz Başlatıcı kodu üretir.

### <a name="to-create-a-project"></a>Bir proje oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** seçip **Visual C++**, zaten açık değilse.

1. Orta bölmedeki yüklü şablonlar listesinde seçin **Windows konsol uygulaması**.

1. Proje için bir ad girin **adı** kutusu. Bu örnekte, girin *Game*.

   Varsayılan konumu kabul edebilir **konumu** açılır listede farklı bir konum girin veya seçin **Gözat** , projeyi kaydetmek istediğiniz dizine gitmek için düğme.

   Bir proje oluşturduğunuzda, Visual Studio projeyi bir çözümün içine koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. Adı değiştirebilirsiniz **çözüm adı** kutusu, ancak bu örnekte, varsayılan adı bırakın.

1. Seçin **Tamam** projeyi oluşturmak için.

   Visual Studio, yeni çözüm ve proje dosyalarını oluşturur ve onu oluşturulmuş Game.cpp kaynak kodu dosyası düzenleyicisi açılır.

## <a name="organize-projects-and-files"></a>Projeleri ve dosyaları düzenleme

Kullanabileceğiniz **Çözüm Gezgini** projeleri, dosyaları ve çözümünüzdeki diğer kaynakları düzenlemek ve yönetmek için.

Adım adım öğreticinin bu bölümü projeye nasıl sınıf ekleneceğini göstermektedir. Sınıfı eklediğinizde, Visual Studio karşılık gelen .h ve .cpp dosyaları ekler. Sonuçlarda gördüğünüz **Çözüm Gezgini**.

### <a name="to-add-a-class-to-a-project"></a>Bir projeye sınıf eklemek için

1. Varsa **Çözüm Gezgini** penceresi Visual Studio'da, menü çubuğunda görüntülenmez öğesini **görünümü** > **Çözüm Gezgini**.

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

   - Visual Studio'nun ürettiği varsayılan oluşturucuyu değiştirin. Sonra `public:` erişim belirticisi, şuna benzeyen satırı bulun:

      `Cardgame();`

      Bu oluşturucu türünden bir parametre değiştirme `int`, adlandırılmış *oyuncuların*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->`Cardgame(int players);`

   - Varsayılan yıkıcıdan sonra eklemek için bir satır içi bildirim bir `static int` adlı üye işlevi *GetParticipants* , herhangi bir parametre alır ve döndürür `totalParticipants` değeri.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->`static int GetParticipants() { return totalParticipants; }`

   Cardgame.h dosyası, siz değiştirdikten sonra şuna benzemelidir:

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

   Satır `#pragma once` derleyici üstbilgi dosyası yalnızca bir kez dahil etmesini söyler. Daha fazla bilgi için [sonra](../preprocessor/once.md). Bu üstbilgi dosyasındaki diğer C++ anahtar sözcükleri hakkında daha fazla bilgi için bkz. [sınıfı](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [statik](../cpp/storage-classes-cpp.md), ve [genel](../cpp/public-cpp.md).

1. Seçin **Cardgame.cpp** düzenlemek üzere açmak için düzenleme bölmesinin üst sekmesi.

1. Dosyadaki her şeyi silin ve şu kodla değiştirin:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "pch.h"
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

1. İçinde **Game.cpp** Düzenleyicisi penceresinde, mevcut kodu şununla değiştirin:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "pch.h"
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
Bu kod, bir test işlevi ekler `PlayGames`kaynak kodu ve çağrı içinde `main`.

## <a name="build-and-run-your-app-project"></a>Derleme ve uygulama projenizi çalıştırma

Ardından, projeyi oluşturun ve uygulamayı çalıştırın.

### <a name="to-build-and-run-the-project"></a>Projeyi derleyip çalıştırmak için

1. Menü çubuğunda, **derleme** > **Çözümü Derle**.

   Bir derlemenin çıktısı görüntülenir **çıkış** penceresi. Derlemeniz başarılıysa çıktı şuna benzemelidir:

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

1. Menü çubuğunda projeyi çalıştırmak için seçin **hata ayıklama** > **hata ayıklama olmadan Başlat**. Bir konsol penceresi görünür olmalıdır ve çıktı şuna benzemelidir:

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
Konsol penceresini kapatmak için bir tuşa basın.

Tebrikler, bir uygulama projesi ve çözümü başarıyla derlediyseniz. İzlenecek yol, C++ kod projeleri Visual Studio'da derleme hakkında daha fazla bilgi için devam edin.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)<br/>
**Sonraki:** [izlenecek yol: Proje derleme (C++)](../ide/walkthrough-building-a-project-cpp.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>

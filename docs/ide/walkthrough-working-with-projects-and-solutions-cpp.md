---
title: "İzlenecek yol: Projeler ve çözümler (C++) ile çalışma | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a20c0ee933d49465a841b638a8260181d7175ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)

Visual Studio'da nasıl C++ projesi oluşturulduğu, nasıl kod eklendiği ve ardından projenin nasıl oluşturulup çalıştırıldığını burada bulabilirsiniz. Bu adım adım öğreticideki proje, kaç oyuncunun farklı kart oyunları oynadığını izleyen bir programdır.

Visual Studio'da projeler ve çözümler iş düzenlenmiştir. Bir çözüm birden fazla proje içerebilir; örneğin bir DLL ve bu DLL'ye başvuran yürütülebilir bir dosya. Daha fazla bilgi için bkz: [çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="before-you-start"></a>Başlamadan önce

Bu izlenecek yolu tamamlamak için Visual Studio 2017 sürüm 15.3 veya üstü gerekir. Bir kopyasını ihtiyacınız varsa, kısa bir kılavuz şöyledir: [Visual Studio yükleme C++ Destek](../build/vscpp-step-0-installation.md). Bunu henüz yapmadıysanız sonraki adımlar Visual C++ doğru şekilde yüklendiğinden emin olmak için "Hello, World" öğretici ve aracılığıyla yüklenmesinden sonra tüm çalıştığından izleyin.

C++ dili, temellerini ve ne derleyici, bağlayıcı ve hata ayıklayıcı için kullanılan biliyorsanız yardımcı olur. Öğretici, aynı zamanda Windows ve menüleri, iletişim kutuları kullanma konusunda bilgi sahibi varsayar,

## <a name="create-a-project"></a>Proje oluşturma

Proje oluşturmak için önce bir proje türü şablonu seçin. Her proje türü için Visual Studio derleyici ayarları ayarlar ve — türüne bağlı olarak — daha sonra değiştirebilirsiniz başlangıç kodunu oluşturur.

### <a name="to-create-a-project"></a>Bir proje oluşturmak için

1. Menü çubuğunda seçin **Dosya > Yeni > Proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **yüklü** seçip **Visual C++**, zaten açık değilse.

1. Orta bölmede yüklenmiş şablonlar listesinden seçin **Windows konsol uygulaması**.

1. Projede için bir ad girin **adı** kutusu. Bu örnekte, girin **oyun**.

   Varsayılan konumu kabul edebilir **konumu** aşağı açılan listesinde, farklı bir konum girin veya seçin **Gözat** projeyi kaydetmek istediğiniz bir dizine gözatmak için düğmeyi.

   Bir proje oluşturduğunuzda, Visual Studio Proje bir çözümde koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. Adını değiştirebilirsiniz **çözüm adı** kutusu, ancak bu örnek için varsayılan adı bırakın.

1. Seçin **Tamam** projesi oluşturmak için düğmesi.

   Visual Studio yeni çözüm ve proje dosyalarını oluşturur ve bunu oluşturulan Game.cpp kaynak kodu dosyasının Düzenleyicisi'ni açar.

## <a name="organize-projects-and-files"></a>Projeler ve dosyaları düzenleme

Kullanabileceğiniz **Çözüm Gezgini** düzenlemek ve projeleri, dosyaları ve diğer kaynakları çözümünüzdeki yönetmek için.

Adım adım öğreticinin bu bölümü projeye nasıl sınıf ekleneceğini göstermektedir. Sınıf eklediğinizde, Visual Studio karşılık gelen .h ve .cpp dosyaları ekler. Sonuçları görebilirsiniz **Çözüm Gezgini**.

### <a name="to-add-a-class-to-a-project"></a>Bir projeye sınıf eklemek için

1. Varsa **Çözüm Gezgini** penceresi gösterilmesi için Visual Studio menü çubuğunda, seçin **Görünüm > Çözüm Gezgini**.

1. İçinde **Çözüm Gezgini**seçin **oyun** projesi. Menü çubuğunda seçin **Proje > sınıfı Ekle**.

1. İçinde **sınıfı Ekle** iletişim kutusunda, girin *Cardgame* içinde **sınıf adı** kutusu. Varsayılan dosya adlarını ve ayarlarını değiştirmeyin. Seçin **Tamam** düğmesi.

   Visual Studio yeni dosyaları oluşturur ve bunları projenize ekler. Bunları görebilirsiniz **Çözüm Gezgini** penceresi. Cardgame.h ve Cardgame.cpp dosyaları Düzenleyicisi'nde açılır.

1. Cardgame.h dosyasını düzenleyin ve bu değişiklikleri yapın:

   - Sınıf tanımının açılış ayracından sonra iki özel veri üyesi ekleyin.
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio'nun ürettiği varsayılan oluşturucuyu değiştirin. Sonra `public:` belirticisi erişmek için şöyle satırı bulun:

      `Cardgame();`

      Bu oluşturucu türü tek bir parametre almalıdır değiştirmek `int`, adlandırılmış *oynatıcıları*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - Bir satır içi bildirimi için varsayılan yıkıcı sonra eklemek bir `static int` adlı üye işlevi *GetParticipants* parametre almayan ve döndürür `totalParticipants` değeri.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

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
       ~Cardgame(void);
       static int GetParticipants() { return totalParticipants; }
   };
   ```

   Satır `#pragma once` yalnızca bir kez üst bilgi dosyasını dahil bildirir. Daha fazla bilgi için bkz: [sonra](../preprocessor/once.md). Bu üstbilgi dosyasında diğer C++ anahtar sözcükleri hakkında daha fazla bilgi için bkz: [sınıfı](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [statik](../cpp/storage-classes-cpp.md), ve [ortak](../cpp/public-cpp.md).

1. Seçin **Cardgame.cpp** düzenlemek üzere açmak için düzenleme bölmesinin üst sekmesini.

1. Dosyadaki her şeyi silin ve şu kodla değiştirin:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "stdafx.h"
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
   > Kod girerken otomatik tamamlamayı kullanabilirsiniz. Örneğin, klavye bu kodu girerseniz, girdiğiniz *pl* veya *Sigortalanan Top* ve Ctrl + Ara çubuğu tuşlarına basın. Otomatik Tamamlama girer `players` veya `totalParticipants` sizin için.

## <a name="add-test-code-to-your-main-function"></a>Ana işlevinizi test kodu ekleyin

Bazı kodlar yeni işlevler testleri uygulamanıza ekleyin.

### <a name="to-add-test-code-to-the-project"></a>Test kodu projeye eklemek için

1. Game.cpp Düzenleyicisi penceresinde, varolan kod bu ile değiştirin:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "stdafx.h"
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
Bu kod bir test işlevi ekler `PlayGames`, kaynak kodu ve çağrıları içinde `main`. 

## <a name="build-and-run-your-app-project"></a>Uygulama projesini derlemeyi ve çalıştırmayı

Ardından, projeyi oluşturun ve uygulamayı çalıştırın.

### <a name="to-build-and-run-the-project"></a>Projeyi derleyip çalıştırmak için

1. Menü çubuğunda seçin **Yapı > Yapı çözümü**.

   Derleme çıktısı görüntülenir **çıkış** penceresi. Derlemeniz başarılıysa çıktı şuna benzemelidir:

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   **Çıkış** penceresi yapı yapılandırmasına bağlı olarak farklı adımlar gösterebilir, ancak Proje yapı başarılı olursa, son satırında gösterilen çıkış benzemelidir.

   Derleme başarısız oldu, önceki adımlarda gösterilen kodu kodunuzu karşılaştırın.

1. Menü çubuğunda proje çalıştırmak için tercih **hata ayıklama > hata ayıklama olmadan Başlat**. Bir konsol penceresi görünür olmalıdır ve çıktı şuna benzemelidir:

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
Konsol penceresini kapatmak için bir tuşa basın.

Tebrikler, bir uygulama proje ve çözüm başarıyla oluşturuncaya. İzlenecek yol Visual Studio'da C++ kodu projeleri oluşturma hakkında daha fazla bilgi için devam edin.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
**Sonraki:** [izlenecek yol: Proje derleme (C++)](../ide/walkthrough-building-a-project-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)  
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)
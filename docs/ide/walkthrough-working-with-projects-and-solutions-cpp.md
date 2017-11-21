---
title: "İzlenecek yol: Projeler ve çözümler (C++) ile çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6b30cd4885d5fdd65831c8044a088fcb87b52ae3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>İzlenecek Yol: Projelerle ve Çözümlerle Çalışma (C++)
Visual Studio'da nasıl C++ projesi oluşturulduğu, nasıl kod eklendiği ve ardından projenin nasıl oluşturulup çalıştırıldığını burada bulabilirsiniz. Bu adım adım öğreticideki proje, kaç oyuncunun farklı kart oyunları oynadığını izleyen bir programdır.  
  
 Visual Studio'da projeler ve çözümler iş düzenlenmiştir. Bir çözüm birden fazla proje içerebilir; örneğin bir DLL ve bu DLL'ye başvuran yürütülebilir bir dosya. Daha fazla bilgi için bkz: [çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio).  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.  
  
## <a name="creating-a-project"></a>Proje Oluşturma  
 Proje oluşturmak için önce bir proje türü şablonu seçin. Her proje türü için Visual Studio derleyici ayarları ayarlar ve — türüne bağlı olarak — daha sonra değiştirebilirsiniz başlangıç kodunu oluşturur.  
  
#### <a name="to-create-a-project"></a>Bir proje oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **yüklü şablonlar** düğümünü genişletin **Visual C++** düğümünü ve ardından **Win32**.  
  
3.  Orta bölmede yüklenmiş şablonlar listesinden seçin **Win32 konsol uygulaması**.  
  
4.  Projede için bir ad girin **adı** kutusu. Bu örnekte, girin **oyun**.  
  
     Varsayılan konumu kabul edebilir **konumu** aşağı açılan listesinde, farklı bir konum girin veya seçin **Gözat** projeyi kaydetmek istediğiniz bir dizine gözatmak için düğmeyi.  
  
     Bir proje oluşturduğunuzda, Visual Studio Proje bir çözümde koyar. Varsayılan olarak çözüm proje ile aynı ada sahiptir. Adını değiştirebilirsiniz **çözüm adı** kutusu, ancak bu örnek için varsayılan adı bırakın.  
  
     Seçin **Tamam** başlatmak için düğmesini **Win32 Uygulama Sihirbazı'nı**.  
  
5.  Üzerinde **genel bakış** sayfasında **Win32 Uygulama Sihirbazı'nı**, seçin **sonraki** düğmesi.  
  
6.  Üzerinde **uygulama ayarları** sayfasında **uygulama türü**seçin **konsol uygulaması**. Altında **ek seçenekler**, Temizle **önceden derlenmiş üstbilgi** ayarı ve ardından **boş proje** ayarı. Seçin **son** projesi oluşturmak için düğmesi.  
  
     Artık bir projeniz var, ancak henüz kaynak kodu dosyaları yok.  
  
## <a name="organizing-projects-and-files-in-a-solution"></a>Bir Çözüm İçindeki Projeleri ve Dosyaları Düzenleme  
 Kullanabileceğiniz **Çözüm Gezgini** düzenlemek ve projeleri, dosyaları ve diğer kaynakları çözümünüzdeki yönetmek için.  
  
 Adım adım öğreticinin bu bölümü projeye nasıl sınıf ekleneceğini göstermektedir. Sınıf eklediğinizde, Visual Studio karşılık gelen .h ve .cpp dosyaları ekler. Sonra sınıfları test eden ana program için yeni bir kaynak kodu dosyası eklersiniz.  
  
#### <a name="to-add-a-class-to-a-project"></a>Bir projeye sınıf eklemek için  
  
1.  Varsa **Çözüm Gezgini** olan gösterilmiyorsa, menü çubuğunda seçin **Görünüm**, **Çözüm Gezgini**.  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **üstbilgi dosyaları** klasörünü ve ardından **Ekle**, **sınıfı**.  
  
     Sol bölmesinde **sınıfı Ekle** iletişim kutusunda, genişletin **Visual C++** düğümü ve select **C++**ve ardından Ortabölmedeyüklenmişşablonlarlistesindenseçin **C++ sınıfı**. Seçin **Ekle** düğmesi.  
  
3.  İçinde **genel C++ sınıfı Sihirbazı**, girin **Cardgame** içinde **sınıf adı** kutusu. Varsayılan dosya adlarını ve ayarlarını değiştirmeyin. Seçin **son** düğmesi.  
  
4.  Cardgame.h dosyası düzenleyicide açılır. Şu değişiklikleri yapın:  
  
    -   Sınıf tanımının açılış ayracından sonra iki özel veri üyesi ekleyin.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)]  
  
    -   Visual Studio'nun ürettiği varsayılan oluşturucuyu değiştirin. Sonra `public:` belirticisi erişmek için şöyle satırı bulun:  
  
         `Cardgame(void);`  
  
         Türünde bir parametre gerçekleştirecek şekilde değiştirme `int`, adlandırılmış **oynatıcıları**.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]  
  
    -   Adlı bir statik int üye işlevi için bir satır içi bildirimi varsayılan yıkıcı sonra eklemek **GetParticipants** parametre almayan ve döndürür **totalParticipants** değeri.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]  
  
5.  Cardgame.h dosyası, siz değiştirdikten sonra şuna benzemelidir:  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]  
  
     Satır `#pragma once` yalnızca bir kez dosya eklemek için derleyici söyler. Daha fazla bilgi için bkz: [sonra](../preprocessor/once.md).  
  
     Bu üstbilgi dosyasında diğer C++ anahtar sözcükleri hakkında daha fazla bilgi için bkz: [sınıfı](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [statik](../cpp/storage-classes-cpp.md), ve [ortak](../cpp/public-cpp.md).  
  
6.  Seçin **Cardgame.cpp** sekmesini düzenleme bölmesinde düzenlemek için açın.  
  
7.  Dosyadaki her şeyi silin ve şu kodla değiştirin:  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]  
  
    > [!NOTE]
    >  Kod girerken otomatik tamamlamayı kullanabilirsiniz. Örneğin, girdiğiniz Bu kod, girdiğiniz **pl** veya **Sigortalanan Top** ve otomatik tamamlama tamamlayabilmesi Ctrl + Ara çubuğu tuşlarına basın girme `players` veya `totalParticipants` sizin için.  
  
     Hakkında bilgi için `#include`, bkz: [#include yönergesi (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).  
  
## <a name="adding-a-source-file"></a>Kaynak Dosya Ekleme  
 Şimdi, sınıfı test eden ana program için bir kaynak kodu dosyası ekleyin.  
  
#### <a name="to-add-a-new-source-file"></a>Yeni bir kaynak dosya eklemek için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **kaynak dosyaları** klasörünü ve ardından **Ekle**, **yeni öğe**.  
  
     İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede, genişletin **yüklü** düğümünü genişletin **Visual C++** düğümünü ve ardından **kod**. Orta bölmede seçin **C++ dosyasına (.cpp)**.  
  
2.  Girin **TestGames.cpp** içinde **adı** kutusuna ve ardından **Ekle** düğmesi.  
  
3.  TestGames.cpp düzenleme penceresinde aşağıdaki kodu girin.  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]  
  
## <a name="building-and-running-a-project"></a>Bir Projeyi Derleme ve Çalıştırma  
 Şimdi, projeyi derleyin ve uygulamayı çalıştırın.  
  
#### <a name="to-build-and-run-the-project"></a>Projeyi derleyip çalıştırmak için  
  
1.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
    > [!NOTE]
    >  Görüntülenmez bir Express sürümünü kullanıyorsanız, bir **yapı** menü çubuğundaki menüsü seçin **Araçları**, **ayarları**, **Uzman ayarları**etkinleştirmek için.  
  
     Derleme çıktısı görüntülenir **çıkış** penceresi. Derlemeniz başarılıysa çıktı şuna benzemelidir:  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Cardgame.cpp  
    1>  Generating Code...  
    1>  Game.vcxproj -> c:\users\username\documents\visual studio\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
  
    ```  
  
     **Çıkış** penceresi edition ve yapı yapılandırma bağlı olarak farklı adımlar gösterebilir, ancak Proje yapı başarılı olursa, son satırında gösterilen çıkış benzemelidir.  
  
     Derlemeniz başarılı olmadıysa, kodunuzu önceki adımlarda verilen kodla karşılaştırın.  
  
2.  Menü çubuğunda proje çalıştırmak için tercih **hata ayıklama**, **hata ayıklama olmadan Başlat**. Çıkış şuna benzemelidir:  
  
    ```Output  
    4 players have started a new game.  There are now 4 players in total.  
    8 players have started a new game.  There are now 12 players in total.  
    1 players have started a new game.  There are now 13 players in total.  
    5 players have started a new game.  There are now 18 players in total.  
    ```  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md). **Sonraki:**[izlenecek yol: Proje derleme (C++)](../ide/walkthrough-building-a-project-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ programları oluşturma](../build/building-c-cpp-programs.md)
---
title: 'İzim: Statik kitaplık oluşturma ve kullanma (C++)'
description: Visual Studio'da statik kitaplık (.lib) oluşturmak için C++ kullanın.
ms.custom: get-started-article
ms.date: 04/13/2020
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.openlocfilehash: 7148cc1de7c06ae57d61560311b342a1fc9dda1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335145"
---
# <a name="walkthrough-create-and-use-a-static-library"></a>Walkthrough: Statik kitaplık oluşturma ve kullanma

Bu adım adım gözden geçirme, C++ uygulamalarıyla kullanılmak üzere statik bir kitaplık (.lib dosyası) nasıl oluşturulacak gösterilmektedir. Statik kitaplık kullanmak, kodu yeniden kullanmak için harika bir yoldur. İşlevsellik gerektiren her uygulamada aynı yordamları yeniden uygulamak yerine, bunları statik bir kitaplıkta bir kez yazıp uygulamalardan başvurursunuz. Statik kitaplıktan bağlanan kod uygulamanızın bir parçası olur—kodu kullanmak için başka bir dosya yüklemeniz gerekmez.

Bu gözden geçirme şu görevleri kapsar:

- [Statik kitaplık projesi oluşturma](#CreateLibProject)

- [Statik kitaplık bir sınıf ekleme](#AddClassToLib)

- [Statik kitaplık başvurularını içeren bir C++ konsol uygulaması oluşturma](#CreateAppToRefTheLib)

- [Uygulamadaki statik kitaplıktan işlevselliği kullanma](#UseLibInApp)

- [Uygulamayı çalıştırma](#RunApp)

## <a name="prerequisites"></a>Ön koşullar

C++ dilinin temellerinin anlaşılması.

## <a name="create-a-static-library-project"></a><a name="CreateLibProject"></a>Statik kitaplık projesi oluşturma

Projenin nasıl oluşturulacağına ilişkin talimatlar Visual Studio'nun sizin sürüme bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-static-library-project-in-visual-studio-2019"></a>Visual Studio 2019'da statik bir kütüphane projesi oluşturmak için

1. Menü çubuğunda, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **Kitaplık**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Windows Masaüstü Sihirbazı'nı**seçin ve **ardından İleri'yi**seçin.

1. Yeni **proje sayfanızı Yapılandır'da,** proje için bir ad belirtmek için **Proje adı** kutusuna *MathLibrary* girin. **Çözüm ad** kutusuna *StaticMath'i* girin. **Windows Desktop Project** iletişim kutusunu açmak için **Oluştur** düğmesini seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türü**altında **Statik Kitaplık (.lib) seçeneğini belirleyin.**

1. **Ek seçenekler**altında, işaretliyse **Önceden Derlenmiş üstbilgi** onay kutusunun işaretlerini kaldırın. Boş **proje** kutusunu işaretleyin.

1. Projeyi oluşturmak için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-static-library-project-in-visual-studio-2017"></a>Visual Studio 2017'de statik kütüphane projesi oluşturmak için

1. Menü çubuğunda **Yeni** > **Proje** **yi seçin.** >

1. Yeni **Proje** iletişim **kutusunda, Yüklü** > **Visual C++** > **Windows Desktop'ı**seçin. Orta bölmede Windows **Masaüstü Sihirbazı'nı**seçin.

1. Ad kutusunda proje için bir ad belirtin—örneğin, *MathLibrary* **—Ad** kutusunda. Çözüm için bir ad belirtin —örneğin, *StaticMath* **—Çözüm Adı** kutusunda. **Tamam** düğmesini seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türü**altında **Statik Kitaplık (.lib) seçeneğini belirleyin.**

1. **Ek Seçenekler**altında, işaretliyse **Önceden Derlenmiş üstbilgi** onay kutusunun işaretlerini kaldırın. Boş **proje** kutusunu işaretleyin.

1. Projeyi oluşturmak için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-static-library-project-in-visual-studio-2015"></a>Visual Studio 2015'te statik bir kütüphane projesi oluşturmak için

1. Menü çubuğunda **Yeni** > **Proje** **yi seçin.** >

1. Yeni **Proje** iletişim **kutusunda, Yüklü** > **Şablonlar** > **Visual C++** > **Win32'yi**seçin. Orta bölmede **Win32 Konsol Uygulaması'nı**seçin.

1. Ad kutusunda proje için bir ad belirtin—örneğin, *MathLibrary* **—Ad** kutusunda. Çözüm için bir ad belirtin —örneğin, *StaticMath* **—Çözüm Adı** kutusunda. **Tamam** düğmesini seçin.

1. **Win32 Uygulama Sihirbazı'nda** **Next'i**seçin.

1. Uygulama **Ayarları** sayfasında, **Uygulama türü**altında **Statik kitaplığı**seçin. **Ek seçenekler**altında, **Önceden Derlenmiş üstbilgi** onay kutusunun işaretlerini kaldırın. Projeyi oluşturmak için **Finish'i** seçin.

::: moniker-end

## <a name="add-a-class-to-the-static-library"></a><a name="AddClassToLib"></a>Statik kitaplık bir sınıf ekleme

### <a name="to-add-a-class-to-the-static-library"></a>Statik kitaplıya sınıf eklemek için

1. Yeni bir sınıf için üstbilgi dosyası oluşturmak için, **Solution Explorer'daki** **MathLibrary** projesinin kısayol menüsünü açmak için sağ tıklatın ve ardından**Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **Visual C++** > **Kodu'nu**seçin. Orta bölmede **Üstbilgi Dosyası (.h) seçeneğini belirleyin.** Üstbilgi dosyası için bir ad belirtin (örneğin, *MathLibrary.h*— ve sonra **Ekle** düğmesini seçin. Neredeyse boş bir üstbilgi dosyası görüntülenir.

1. Ekleme, çıkarma, çarpma `Arithmetic` ve bölme gibi yaygın matematiksel işlemleri yapmak için adlı sınıf için bir bildirim ekleyin. Kod benzer olmalıdır:

    ```cpp
    // MathLibrary.h
    #pragma once

    namespace MathLibrary
    {
        class Arithmetic
        {
        public:
            // Returns a + b
            static double Add(double a, double b);

            // Returns a - b
            static double Subtract(double a, double b);

            // Returns a * b
            static double Multiply(double a, double b);

            // Returns a / b
            static double Divide(double a, double b);
        };
    }
    ```

1. Yeni sınıf için kaynak dosyası oluşturmak **için, Çözüm Gezgini'ndeki** **MathLibrary** projesinin kısayol menüsünü açın ve ardından**Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda, orta bölmede **C++ Dosyası (.cpp)** seçeneğini belirleyin. Kaynak dosya için bir ad belirtin —örneğin, *MathLibrary.cpp*— ve sonra **Ekle** düğmesini seçin. Boş bir kaynak dosyası görüntülenir.

1. Sınıf `Arithmetic`için işlevselliği uygulamak için bu kaynak dosyayı kullanın. Kod benzer olmalıdır:

    ```cpp
    // MathLibrary.cpp
    // compile with: cl /c /EHsc MathLibrary.cpp
    // post-build command: lib MathLibrary.obj

    #include "MathLibrary.h"

    namespace MathLibrary
    {
        double Arithmetic::Add(double a, double b)
        {
            return a + b;
        }

        double Arithmetic::Subtract(double a, double b)
        {
            return a - b;
        }

        double Arithmetic::Multiply(double a, double b)
        {
            return a * b;
        }

        double Arithmetic::Divide(double a, double b)
        {
            return a / b;
        }
    }
    ```

1. Statik kitaplığı oluşturmak için menü çubuğunda **Yapı** > **Çözümünü** seçin. Yapı, diğer programlar tarafından kullanılabilecek bir statik kitaplık, *MathLibrary.lib*oluşturur.

   > [!NOTE]
   > Visual Studio komut satırı üzerine inşa ettiğinizde, programı iki adımda oluşturmanız gerekir. İlk olarak, kodu derlemek ve `cl /c /EHsc MathLibrary.cpp` *MathLibrary.obj*adlı bir nesne dosyası oluşturmak için çalıştırın. (Komut `cl` derleyici, CL.exe çağırır ve `/c` seçenek bağlamadan derleme belirtir. Daha fazla bilgi için bkz: [/c (Bağlamadan Derle)](../build/reference/c-compile-without-linking.md).) İkinci olarak, kodu bağlamak ve statik kitaplık `lib MathLibrary.obj` *MathLibrary.lib*oluşturmak için çalıştırın. (Komut `lib` Kitaplık Yöneticisi, Lib.exe çağırır. Daha fazla bilgi için [LIB Başvurusu'na](../build/reference/lib-reference.md)bakın.)

## <a name="create-a-c-console-app-that-references-the-static-library"></a><a name="CreateAppToRefTheLib"></a>Statik kitaplık başvurularını içeren bir C++ konsol uygulaması oluşturma

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2019"></a>Visual Studio 2019'daki statik kitaplığı referans alan bir C++ konsol uygulaması oluşturmak için

1. **Çözüm Gezgini'nde,** kısayol menüsünü açmak için üst düğüm, **Çözüm 'StaticMath'** üzerine sağ tıklayın. Yeni Proje Ekle iletişim kutusunu açmak için**Yeni Proje** **Ekle'yi** > seçin. **Add a New Project**

1. İletişim kutusunun üst kısmında, **Proje türü** filtresini **Konsol'a**ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Konsol Uygulaması'nı** seçin ve **ardından İleri'yi**seçin. Sonraki sayfada, proje için bir ad belirtmek için **Ad** kutusuna *MathClient* girin.

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

1. Bir konsol uygulaması oluşturduktan sonra, sizin için boş bir program oluşturulur. Kaynak dosyanın adı, daha önce seçtiğiniz adla aynıdır. Örnekte, adı `MathClient.cpp`.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2017"></a>Visual Studio 2017'deki statik kitaplığı referans alan bir C++ konsol uygulaması oluşturmak için

1. **Çözüm Gezgini'nde,** kısayol menüsünü açmak için üst düğüm, **Çözüm 'StaticMath'** üzerine sağ tıklayın. Yeni Proje Ekle iletişim kutusunu açmak için**Yeni Proje** **Ekle'yi** > seçin. **Add a New Project**

1. Yeni **Proje Ekle** iletişim **kutusunda, Yüklü** > **Görsel C++** > **Windows Desktop'ı**seçin. Orta bölmede Windows **Masaüstü Sihirbazı'nı**seçin.

1. Ad kutusunda proje için bir ad belirtin—örneğin, *MathClient* **—.** **Tamam** düğmesini seçin.

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türü**altında **Konsol Uygulaması(.exe) seçeneğini belirleyin.**

1. **Ek Seçenekler**altında, işaretliyse **Önceden Derlenmiş üstbilgi** onay kutusunun işaretlerini kaldırın.

1. Projeyi oluşturmak için **Tamam'ı** seçin.

1. Bir konsol uygulaması oluşturduktan sonra, sizin için boş bir program oluşturulur. Kaynak dosyanın adı, daha önce seçtiğiniz adla aynıdır. Örnekte, adı `MathClient.cpp`.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2015"></a>Visual Studio 2015'teki statik kitaplığı referans alan bir C++ konsol uygulaması oluşturmak için

1. **Çözüm Gezgini'nde,** kısayol menüsünü açmak için üst düğüm, **Çözüm 'StaticMath'** üzerine sağ tıklayın. Yeni Proje Ekle iletişim kutusunu açmak için**Yeni Proje** **Ekle'yi** > seçin. **Add a New Project**

1. Yeni **Proje Ekle** iletişim **kutusunda, Yüklü** > **Visual C++** > **Win32'yi**seçin. Orta bölmede **Win32 Konsol Uygulaması'nı**seçin.

1. Ad kutusunda proje için bir ad belirtin—örneğin, *MathClient* **—.** **Tamam** düğmesini seçin.

1. **Win32 Uygulama Sihirbazı** iletişim kutusunda **İleri'yi**seçin.

1. Uygulama **Ayarları** sayfasında, **Uygulama türü**altında, **Konsol uygulamasının** seçildiğinden emin olun. **Ek seçenekler**altında, **Önceden Derlenmiş üstbilginin**işaretlerini kaldırın, ardından **Boş Proje** onay kutusunu işaretleyin. Projeyi oluşturmak için **Finish'i** seçin.

1. Boş projeye kaynak dosyası eklemek **için, Solution Explorer'daki** **MathClient** projesinin kısayol menüsünü açmak için sağ tıklatın ve ardından **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **Visual C++** > **Kodu'nu**seçin. Orta bölmede **C++ Dosyası (.cpp)** seçeneğini belirleyin. Kaynak dosya için bir ad belirtin —örneğin, *MathClient.cpp*— ve sonra **Ekle** düğmesini seçin. Boş bir kaynak dosyası görüntülenir.

::: moniker-end

## <a name="use-the-functionality-from-the-static-library-in-the-app"></a><a name="UseLibInApp"></a>Uygulamadaki statik kitaplıktan işlevselliği kullanma

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Uygulamadaki statik kitaplıktan işlevselliği kullanmak için

1. Statik kitaplıktaki matematik yordamlarını kullanamadan önce başvuruda bulunmalısınız. **Solution Explorer'daki** **MathClient** projesinin kısayol menüsünü açın ve ardından**Başvuru** **Ekle'yi** > seçin.

1. **Başvuru Ekle** iletişim kutusu, başvuruyapabileceğiniz kitaplıkları listeler. **Projeler** sekmesi, geçerli çözümdeki projeleri ve başvurulan kitaplıkları listeler. **Projeler** sekmesini açın, **MathLibrary** onay kutusunu seçin ve sonra **Tamam** düğmesini seçin.

1. Üstbilgi `MathLibrary.h` dosyasına başvurmak için, dahil edilen dizinler yolunu değiştirmeniz gerekir. **Solution Explorer'da**kısayol menüsünü açmak için **MathClient'a** sağ tıklayın. **MathClient Özellik Sayfaları** iletişim kutusunu açmak için **Özellikler'i** seçin.

1. **MathClient Özellik Sayfaları** iletişim kutusunda, **Yapılandırma** açılır tüm **yapılandırmaları**ayarlayın. **Platformu** **Tüm Platformlara**indirin.

1. Yapılandırma **Özellikleri** > **C/C++** > **Genel** özellik sayfasını seçin. Ek **İçki Dizinleri** özelliğinde, **MathLibrary** dizininin yolunu belirtin veya bunun için göz atın.

   Dizin yoluna göz atmak için:

   1. Ek **İçdiziler** özellik açılır listesini açın ve sonra **Edit'i**seçin.

   1. Ek **Dizinler Ekle** iletişim kutusunda, metin kutusunun üst kısmında çift tıklatın. Ardından satırın sonundaki elips düğmesini (**...**) seçin.

   1. **Dizin Seç** iletişim kutusunda, bir düzeyyukarı gidin ve sonra **MathLibrary** dizinini seçin. Ardından seçiminizi kaydetmek için **Klasörü Seç** düğmesini seçin.

   1. Ek **Dizinler Ekle** iletişim kutusunda **Tamam** düğmesini seçin.

   1. Özellik **Sayfaları** iletişim kutusunda, projedeki değişikliklerinizi kaydetmek için **Tamam** düğmesini seçin.

1. Artık bu uygulamadaki `Arithmetic` sınıfı, başlığı kodunuza ekleyerek `#include "MathLibrary.h"` kullanabilirsiniz. İçeriğini bu `MathClient.cpp` kodla değiştirin:

    ```cpp
    // MathClient.cpp
    // compile with: cl /EHsc MathClient.cpp /link MathLibrary.lib

    #include <iostream>
    #include "MathLibrary.h"

    int main()
    {
        double a = 7.4;
        int b = 99;

        std::cout << "a + b = " <<
            MathLibrary::Arithmetic::Add(a, b) << std::endl;
        std::cout << "a - b = " <<
            MathLibrary::Arithmetic::Subtract(a, b) << std::endl;
        std::cout << "a * b = " <<
            MathLibrary::Arithmetic::Multiply(a, b) << std::endl;
        std::cout << "a / b = " <<
            MathLibrary::Arithmetic::Divide(a, b) << std::endl;

        return 0;
    }
    ```

1. Çalıştırılabilir'i oluşturmak için menü çubuğunda **Yapı** > **Çözüm'üne** çözüm oluşturun'u seçin.

## <a name="run-the-app"></a><a name="RunApp"></a>Uygulamayı çalıştırın

### <a name="to-run-the-app"></a>Uygulamayı çalıştırmak için

1. **MathClient'ın** varsayılan proje olarak seçildiğinden emin olun. Seçmek için, **Solution Explorer'da** **MathClient** için kısayol menüsünü açmak için sağ tıklatın ve ardından **StartUp Project olarak ayarla'yı**seçin.

1. Projeyi çalıştırmak için menü çubuğunda Hata**Ayıklama Başlatma'yı** **seçin.** >  Çıktı benzer olmalıdır:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[Masaüstü Uygulamaları (Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>

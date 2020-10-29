---
title: 'İzlenecek yol: Statik kitaplık oluşturma ve kullanma (C++)'
description: Visual Studio 'da bir statik kitaplık (. lib) oluşturmak için C++ kullanın.
ms.custom: get-started-article
ms.date: 04/13/2020
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.openlocfilehash: 6cb379baafc506570b1bdc1b286b35c40f8cd0d8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924377"
---
# <a name="walkthrough-create-and-use-a-static-library"></a>İzlenecek yol: statik kitaplık oluşturma ve kullanma

Bu adım adım izlenecek yol, C++ uygulamalarıyla kullanılmak üzere statik bir kitaplığın (. lib dosyası) nasıl oluşturulacağını gösterir. Statik kitaplık kullanmak, kodu yeniden kullanmak için harika bir yoldur. İşlevselliği gerektiren her uygulamada aynı yordamları yeniden uygulamak yerine, bunları statik bir kitaplığa bir kez yazar ve ardından uygulamalardan başvurar. Statik kitaplıktan bağlantılı kod uygulamanızın bir parçası haline gelir — kodu kullanmak için başka bir dosya yüklemek zorunda değilsiniz.

Bu izlenecek yol aşağıdaki görevleri içerir:

- [Statik kitaplık projesi oluşturma](#CreateLibProject)

- [Statik kitaplığa bir sınıf ekleyin](#AddClassToLib)

- [Statik kitaplığa başvuran bir C++ konsol uygulaması oluşturma](#CreateAppToRefTheLib)

- [Uygulamadaki statik kitaplıktan işlevselliği kullanın](#UseLibInApp)

- [Uygulamayı çalıştırma](#RunApp)

## <a name="prerequisites"></a>Önkoşullar

C++ dilinin temellerini anlama.

## <a name="create-a-static-library-project"></a><a name="CreateLibProject"></a> Statik kitaplık projesi oluşturma

Projenin nasıl oluşturulacağı hakkında yönergeler, Visual Studio sürümünüze bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="msvc-160"

### <a name="to-create-a-static-library-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de statik kitaplık projesi oluşturmak için

1. **File** > **New** > **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında,  **dili** **C++** olarak ayarlayın, **platformu** **Windows** 'a ayarlayın ve **proje türünü** **kitaplık** olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Windows Masaüstü Sihirbazı** ' nı seçin ve ardından **İleri** ' yi seçin.

1. **Yeni projenizi yapılandırın** sayfasında, proje için bir ad belirtmek üzere **Proje adı** kutusuna *MathLibrary* girin. **Çözüm adı** kutusuna *staticmath* girin. **Windows Masaüstü projesi** iletişim kutusunu açmak için **Oluştur** düğmesini seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türü** altında, **statik kitaplık (. lib)** öğesini seçin.

1. **Ek seçenekler** altında, **önceden derlenmiş üst bilgi** onay kutusunun işaretini kaldırın. **Boş proje** kutusunu işaretleyin.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="msvc-150"

### <a name="to-create-a-static-library-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de statik kitaplık projesi oluşturmak için

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje** ' yi seçin.

1. **Yeni proje** iletişim kutusunda, **Installed**  >  **Visual C++**  >  **Windows Masaüstü** Visual C++ yüklü ' ı seçin. Orta bölmede **Windows Masaüstü Sihirbazı** ' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MathLibrary* ) belirtin. Çözüm **adı** kutusunda çözüm için bir ad (örneğin, *staticmath* ) belirtin. **Tamam** düğmesini seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türü** altında, **statik kitaplık (. lib)** öğesini seçin.

1. **Ek seçenekler** altında, **önceden derlenmiş üst bilgi** onay kutusunun işaretini kaldırın. **Boş proje** kutusunu işaretleyin.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="msvc-140"

### <a name="to-create-a-static-library-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de statik kitaplık projesi oluşturmak için

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje** ' yi seçin.

1. **Yeni proje** iletişim kutusunda, **yüklü**  >  **Şablonlar**  >  **Visual C++**  >  **Win32** ' i seçin. Orta bölmede **Win32 konsol uygulaması** ' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MathLibrary* ) belirtin. Çözüm **adı** kutusunda çözüm için bir ad (örneğin, *staticmath* ) belirtin. **Tamam** düğmesini seçin.

1. **Win32 uygulama sihirbazında** **İleri** ' yi seçin.

1. **Uygulama ayarları** sayfasında, **uygulama türü** altında, **statik kitaplık** ' ı seçin. **Ek seçenekler** altında, **önceden derlenmiş üstbilgi** onay kutusunun işaretini kaldırın. Projeyi oluşturmak için **son** ' a tıklayın.

::: moniker-end

## <a name="add-a-class-to-the-static-library"></a><a name="AddClassToLib"></a> Statik kitaplığa bir sınıf ekleyin

### <a name="to-add-a-class-to-the-static-library"></a>Statik kitaplığa bir sınıf eklemek için

1. Yeni bir sınıf için üst bilgi dosyası oluşturmak üzere, **Çözüm Gezgini** ' de **MathLibrary** projesinin kısayol menüsünü açmak için sağ tıklayın ve sonra **Add**  >  **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda **Visual C++**  >  **kodu** ' nu seçin. Orta bölmede **üst bilgi dosyası (. h)** öğesini seçin. Üstbilgi dosyası için bir ad belirtin — örneğin, *MathLibrary. h* — ve sonra **Ekle** düğmesini seçin. Neredeyse boş bir üst bilgi dosyası görüntülenir.

1. `Arithmetic`Toplama, çıkarma, çarpma ve bölme gibi genel matematik işlemlerini yapmak için adlı bir sınıf için bildirim ekleyin. Kod şöyle olmalıdır:

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

1. Yeni sınıf için bir kaynak dosyası oluşturmak için, **Çözüm Gezgini** ' de **MathLibrary** projesinin kısayol menüsünü açın ve **Add**  >  **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, Orta bölmede, **C++ dosyası (. cpp)** öğesini seçin. Kaynak dosya için bir ad belirtin — örneğin, *MathLibrary. cpp* — ve sonra **Ekle** düğmesini seçin. Boş bir kaynak dosyası görüntülenir.

1. Sınıfa yönelik işlevselliği uygulamak için bu kaynak dosyayı kullanın `Arithmetic` . Kod şöyle olmalıdır:

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

1. Statik kitaplığı derlemek için, menü çubuğunda **Build**  >  **Build Solution** öğesini seçin. Derleme, diğer programlar tarafından kullanılabilen *MathLibrary. lib* statik bir kitaplığı oluşturur.

   > [!NOTE]
   > Visual Studio komut satırında oluşturduğunuzda, programı iki adımda derlemeniz gerekir. İlk olarak, `cl /c /EHsc MathLibrary.cpp` kodu derlemek ve *MathLibrary. obj* adlı bir nesne dosyası oluşturmak için çalıştırın. ( `cl` Komut, Cl.exe derleyicisini çağırır ve `/c` seçeneği bağlama olmadan derlemeyi belirtir. Daha fazla bilgi için bkz. [/c (bağlama olmadan Derle)](../build/reference/c-compile-without-linking.md).) İkinci olarak, `lib MathLibrary.obj` kodu bağlamak ve *MathLibrary. lib* statik kitaplığını oluşturmak için çalıştırın. ( `lib` Komut, Lib.exe kitaplık yöneticisini çağırır. Daha fazla bilgi için bkz. [LIB Reference](../build/reference/lib-reference.md).)

## <a name="create-a-c-console-app-that-references-the-static-library"></a><a name="CreateAppToRefTheLib"></a> Statik kitaplığa başvuran bir C++ konsol uygulaması oluşturma

::: moniker range="msvc-160"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2019"></a>Visual Studio 2019 ' de statik kitaplığa başvuran bir C++ konsol uygulaması oluşturmak için

1. **Çözüm Gezgini** ' de, üst düğüme sağ tıklayın, **' Staticmath ' çözümü** , kısayol menüsünü açmak için. Yeni proje **Ekle**  >  iletişim kutusunu açmak için **Add a New Project** **Yeni proje** Ekle ' yi seçin.

1. İletişim kutusunun üst kısmında, **Proje türü** filtresini **konsol** olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri** ' yi seçin. Bir sonraki sayfada, proje için bir ad belirtmek üzere **ad** kutusuna *MathClient* girin.

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

1. Bir konsol uygulaması oluşturduktan sonra, sizin için boş bir program oluşturulur. Kaynak dosyanın adı, daha önce seçtiğiniz adla aynıdır. Örnekte, adlandırılır `MathClient.cpp` .

::: moniker-end

::: moniker range="msvc-150"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2017"></a>Visual Studio 2017 ' de statik kitaplığa başvuran bir C++ konsol uygulaması oluşturmak için

1. **Çözüm Gezgini** ' de, üst düğüme sağ tıklayın, **' Staticmath ' çözümü** , kısayol menüsünü açmak için. Yeni proje **Ekle**  >  iletişim kutusunu açmak için **Add a New Project** **Yeni proje** Ekle ' yi seçin.

1. **Yeni Proje Ekle** iletişim kutusunda, **Installed**  >  **Visual C++**  >  **Windows Masaüstü** Visual C++ yüklü ' ı seçin. Orta bölmede **Windows Masaüstü Sihirbazı** ' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MathClient* ) belirtin. **Tamam** düğmesini seçin.

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türü** altında, **konsol uygulaması (. exe)** öğesini seçin.

1. **Ek seçenekler** altında, **önceden derlenmiş üst bilgi** onay kutusunun işaretini kaldırın.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

1. Bir konsol uygulaması oluşturduktan sonra, sizin için boş bir program oluşturulur. Kaynak dosyanın adı, daha önce seçtiğiniz adla aynıdır. Örnekte, adlandırılır `MathClient.cpp` .

::: moniker-end

::: moniker range="msvc-140"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2015"></a>Visual Studio 2015 ' de statik kitaplığa başvuran bir C++ konsol uygulaması oluşturmak için

1. **Çözüm Gezgini** ' de, üst düğüme sağ tıklayın, **' Staticmath ' çözümü** , kısayol menüsünü açmak için. Yeni proje **Ekle**  >  iletişim kutusunu açmak için **Add a New Project** **Yeni proje** Ekle ' yi seçin.

1. **Yeni Proje Ekle** iletişim kutusunda, **Installed**  >  **Visual C++**  >  **Win32** Visual C++ yüklendi ' yi seçin. Orta bölmede **Win32 konsol uygulaması** ' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MathClient* ) belirtin. **Tamam** düğmesini seçin.

1. **Win32 uygulama Sihirbazı** Iletişim kutusunda **İleri** ' yi seçin.

1. **Uygulama ayarları** sayfasında, **uygulama türü** altında, **konsol uygulamasının** seçildiğinden emin olun. **Ek seçenekler** altında, **önceden derlenmiş üstbilginin** Işaretini kaldırın, sonra **boş proje** onay kutusunu işaretleyin. Projeyi oluşturmak için **son** ' a tıklayın.

1. Boş projeye bir kaynak dosyası eklemek için, **Çözüm Gezgini** ' de **MathClient** projesinin kısayol menüsünü açmak için sağ tıklayın ve sonra **Add** > **Yeni öğe** Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda **Visual C++**  >  **kodu** ' nu seçin. Orta bölmede **C++ dosyası (. cpp)** öğesini seçin. Kaynak dosya için bir ad belirtin — örneğin, *MathClient. cpp* — ve sonra **Ekle** düğmesini seçin. Boş bir kaynak dosyası görüntülenir.

::: moniker-end

## <a name="use-the-functionality-from-the-static-library-in-the-app"></a><a name="UseLibInApp"></a> Uygulamadaki statik kitaplıktan işlevselliği kullanın

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Uygulamadaki statik kitaplıktan işlevselliği kullanmak için

1. Statik kitaplıkta matematik yordamlarını kullanabilmeniz için, buna başvurmanız gerekir. **Çözüm Gezgini** ' de **MathClient** projesi için kısayol menüsünü açın ve ardından başvuru **Ekle** ' yi seçin  >  **Reference** .

1. **Başvuru Ekle** iletişim kutusu, başvurekleyebileceğiniz kitaplıkları listeler. **Projeler** sekmesi geçerli çözümdeki projeleri ve bunların başvurdukları kitaplıkları listeler. **Projeler** sekmesini açın, **MathLibrary** onay kutusunu işaretleyin ve ardından **Tamam** düğmesini seçin.

1. `MathLibrary.h`Üstbilgi dosyasına başvurmak için, eklenen dizinler yolunu değiştirmelisiniz. **Çözüm Gezgini** ' de, kısayol menüsünü açmak için **MathClient** ' a sağ tıklayın. **Özellikler** ' i seçerek **MathClient Özellik sayfaları** iletişim kutusunu açın.

1. **MathClient Özellik sayfaları** iletişim kutusunda, **yapılandırma** açılan kutusunu **tüm yapılandırmalar** olarak ayarlayın. **Platform** açılır öğesini **tüm platformlar** olarak ayarlayın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını seçin. **Ek Içerme dizinleri** özelliğinde, **MathLibrary** dizininin yolunu belirtin veya buna gözatamazsınız.

   Dizin yoluna gitmek için:

   1. **Ek ekleme dizinleri** Özellik değeri açılan listesini açın ve ardından **Düzenle** ' yi seçin.

   1. **Ek dizinler Ekle** iletişim kutusunda metin kutusunun en üstüne çift tıklayın. Ardından satırın sonundaki üç nokta düğmesini ( **...** ) seçin.

   1. **Dizin Seç** iletişim kutusunda, bir düzey yukarı gidin ve **MathLibrary** dizinini seçin. Seçiminizi kaydetmek için **Klasör Seç** düğmesini seçin.

   1. **Ek dizinleri Ekle** Iletişim kutusunda **Tamam** düğmesini seçin.

   1. Değişiklikleri projeye kaydetmek için **Özellik sayfaları** Iletişim kutusunda **Tamam** düğmesini seçin.

1. Artık `Arithmetic` Bu uygulamadaki sınıfını `#include "MathLibrary.h"` kodunuza başlık ekleyerek kullanabilirsiniz. İçeriğini `MathClient.cpp` şu kodla değiştirin:

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

1. Yürütülebilir dosyayı oluşturmak için, menü çubuğunda derleme çözümü **Oluştur ' u seçin**  >  **Build Solution** .

## <a name="run-the-app"></a><a name="RunApp"></a> Uygulamayı çalıştırma

### <a name="to-run-the-app"></a>Uygulamayı çalıştırmak için

1. **MathClient** 'in varsayılan proje olarak seçildiğinden emin olun. Bunu seçmek için sağ tıklayıp **Çözüm Gezgini** içindeki **MathClient** için kısayol menüsünü açın ve ardından **Başlangıç projesi olarak ayarla** ' yı seçin.

1. Projeyi çalıştırmak için menü çubuğunda **hata ayıklama**  >  **başlatma hatası olmadan Başlat** ' ı seçin. Çıktı şuna benzemelidir:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: dinamik bağlantı kitaplığı oluşturma ve kullanma (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[Masaüstü Uygulamaları (Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>

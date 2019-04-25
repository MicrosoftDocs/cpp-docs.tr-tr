---
title: 'İzlenecek yol: Bir statik kitaplık (C++) oluşturma ve kullanma'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.author: corob
ms.openlocfilehash: 0d527681abb077a01b3d902c092a21de7a052867
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313625"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>İzlenecek yol: Bir statik kitaplık (C++) oluşturma ve kullanma

Bu adım adım kılavuzda, C++ uygulamaları ile kullanmak için bir statik kitaplık (.lib dosyası) oluşturma işlemini göstermektedir. Statik kitaplık kullanma, kodu yeniden kullanmak için harika bir yoludur. Bir bunları yazdığınız işlevselliği gerektiren her uygulamada aynı yordamları reimplementing yerine statik kitaplıkta saat ve sonra uygulamalardan başvurun. Statik bir kitaplıktan bağlanan kod, uygulamanızın bir parçası olur — kodu kullanmak için başka bir dosya yüklemeniz gerekmez.

Bu izlenecek yol bu görevleri kapsar:

- [Statik kitaplık projesi oluşturma](#CreateLibProject)

- [Statik kitaplığa bir sınıf ekleme](#AddClassToLib)

- [Statik kitaplık başvurusu bir C++ konsol uygulaması oluşturma](#CreateAppToRefTheLib)

- [Uygulama içindeki statik kitaplıkta işlevselliği kullanarak](#UseLibInApp)

- [Uygulamayı çalıştırma](#RunApp)

## <a name="prerequisites"></a>Önkoşullar

Bir C++ dilinin temellerini anlama.

##  <a name="CreateLibProject"></a> Statik kitaplık projesi oluşturma

### <a name="to-create-a-static-library-project"></a>Statik kitaplık projesi oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** > **Visual C++** ve ardından **Windows Masaüstü**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**.

   > [!NOTE]
   > Visual Studio 2017'den daha eski sürümleri için de **yeni proje** iletişim kutusunda **yüklü** > **şablonları**  >  **Visual C++** ve ardından **Win32**. Orta bölmede seçin **Win32 konsol uygulaması**.

1. Proje için bir ad belirleyin — Örneğin, *MathFuncsLib*— içinde **adı** kutusu. Çözüm için bir ad belirleyin — Örneğin, *StaticLibrary*— içinde **çözüm adı** kutusu. Seçin **Tamam** düğmesi.

    - Visual Studio 2017 için

        1. Altında **uygulama türü**seçin **statik kitaplık (.lib)**.

        1. Altında **ek seçenekler**, işaretini kaldırın **önceden derlenmiş üst bilgi** onay kutusu.

        1. Seçin **Tamam** projeyi oluşturmak için.

    - Visual Studio 2017'den daha eski sürümleri

        1. **İleri**'ye tıklayın.

        1. Altında **uygulama türü**seçin **statik kitaplık**. Ardından işaretini kaldırın **önceden derlenmiş üst bilgi** seçin ve kutusunda **son**.

##  <a name="AddClassToLib"></a> Statik kitaplığa bir sınıf ekleme

### <a name="to-add-a-class-to-the-static-library"></a>Statik kitaplığa bir sınıf eklemek için

1. Yeni bir sınıf için bir üstbilgi dosyası oluşturmak için kısayol menüsünü açın **MathFuncsLib** projesi **Çözüm Gezgini**ve ardından **Ekle**  >   **Yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede altında **Visual C++** seçin **kod**. Orta bölmede seçin **üst bilgi dosyası (.h)**. Üstbilgi dosyası için bir ad belirtin — örneğin, *MathFuncsLib.h*— ve ardından **Ekle** düğmesi. Boş üstbilgi dosyası görüntülenir.

1. Adlı bir sınıf ekleyin `MyMathFuncs` toplama, çıkarma, çarpma ve bölme gibi genel matematik işlemlerini yapmak için. Koda benzemelidir:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]

1. Yeni bir sınıf için bir kaynak dosyası oluşturmak için kısayol menüsünü açın **MathFuncsLib** projesi **Çözüm Gezgini**ve ardından **Ekle**  >   **Yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, sol bölmede altında **Visual C++** seçin **kod**. Orta bölmede seçin **C++ dosyası (.cpp)**. Kaynak dosyası için bir ad belirleyin — Örneğin, *MathFuncsLib.cpp*— ve ardından **Ekle** düğmesi. Boş bir kaynak dosyası görüntülenir.

1. Bu kaynak dosyası için işlevselliği uygulamak için kullanmak **MyMathFuncs**. Koda benzemelidir:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]

1. Seçerek statik kitaplığı derleyin **derleme** > **Çözümü Derle** menü çubuğundaki. Derleme başka programlar tarafından kullanılabilen statik kitaplık oluşturur.

   > [!NOTE]
   > Visual Studio komut satırında oluşturduğunuzda, programı iki adımda oluşturmanız gerekir. İlk olarak, çalıştırma `cl /c /EHsc MathFuncsLib.cpp` Kodu derlemek ve adlı bir nesne dosyası oluşturmak için `MathFuncsLib.obj`. ( `cl` Komutu derleyiciyi, cl.exe'yi çalıştırır ve `/c` seçeneği derlemeyi bağlama olmadan belirtir. Daha fazla bilgi için [/c (derleme olmadan bağlamayı)](../build/reference/c-compile-without-linking.md).) İkinci olarak, çalıştırma `lib MathFuncsLib.obj` kodunu bağlamak ve statik kitaplık oluşturmak için `MathFuncsLib.lib`. ( `lib` Komutu Kitaplık Yöneticisi Lib.exe çağırır. Daha fazla bilgi için [LIB başvurusu](../build/reference/lib-reference.md).)

##  <a name="CreateAppToRefTheLib"></a> Statik kitaplık başvurusu bir C++ konsol uygulaması oluşturma

### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>Statik kitaplık başvurusu bir C++ konsol uygulaması oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü** > **Visual C++** ve ardından **Windows Masaüstü**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**.

   > [!NOTE]
   > Visual Studio 2017'den daha eski sürümleri için de **yeni proje** iletişim kutusunda **yüklü** > **şablonları**  >  **Visual C++** ve ardından **Win32**. Orta bölmede seçin **Win32 konsol uygulaması**.

1. Proje için bir ad belirleyin — Örneğin, *MyExecRefsLib*— içinde **adı** kutusu. Açılan liste yanındaki **çözüm**seçin **eklemek için çözüm**. Komut, statik kitaplık içeren çözüme yeni proje ekler. Seçin **Tamam** düğmesi.

    - Visual Studio 2017 için

        1. Altında **uygulama türü**seçin **konsol uygulaması (.exe)**.

        1. Altında **ek seçenekler**, işaretini kaldırın **önceden derlenmiş üst bilgi** onay kutusu.

        1. Seçin **Tamam** projeyi oluşturmak için.

    - Visual Studio 2017'den daha eski sürümleri

        1. **İleri**'ye tıklayın.

        1. Emin **konsol uygulaması** seçilir. Denetleyin ardından **boş proje** kutusuna ve seçin **son**.

##  <a name="UseLibInApp"></a> Uygulama içindeki statik kitaplıkta işlevselliği kullanarak

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Uygulama içindeki statik kitaplıkta işlevselliği kullanmak için

1. Bir konsol uygulaması oluşturduktan sonra boş bir program sizin için oluşturulur. Kaynak dosyasının adı daha önce seçtiğiniz adı ile aynıdır. Örnekte, adlı `MyExecRefsLib.cpp`.

1. Statik kitaplıkta matematik yordamlarını kullanmadan önce başvurmanız gerekir. Kısayol menüsünü açın **MyExecRefsLib** projesi **Çözüm Gezgini**ve ardından **Ekle** > **başvuru**.

1. **Başvuru Ekle** iletişim kutusu başvurabileceğiniz kitaplıkları listeler. **Projeleri** sekmesi projeleri çözüme ve oldukları tüm kitaplıkları listeler. Üzerinde **projeleri** sekmesinde **MathFuncsLib** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.

1. Başvuru `MathFuncsLib.h` üstbilgi dosyasına eklenen dizinlerin yolunu değiştirmeniz gerekir. İçinde **özellik sayfaları** iletişim kutusu için **MyExecRefsLib**, genişletin **yapılandırma özellikleri** düğümünü genişletin **C/C++** düğümünü ve ardından **genel**. Yanındaki **ek içerik dizinleri**, yolunu belirtin **MathFuncsLib** dizini ya da bunu gözatın.

   Dizin yoluna göz atmak için özellik değeri açılan listesini açın ve ardından **Düzenle**. İçinde **ek içerik dizinleri** iletişim kutusunda, metin kutusuna, boş bir satır seçin ve ardından üç nokta düğmesini (**...** ) satırın sonunda. İçinde **dizini Seç** iletişim kutusunda seçin **MathFuncsLib** dizin seçip **klasörü seçin** seçiminizi kaydetmek ve iletişim kutusunu kapatmak için düğme. İçinde **ek içerik dizinleri** iletişim kutusunda **Tamam** düğmesini ve ardından **özellik sayfaları** iletişim kutusunda **Tamam**projeye yaptığınız değişiklikleri kaydetmek için düğme.

1. Artık `MyMathFuncs` sınıfı ekleyerek bu uygulamada `#include "MathFuncsLib.h"` kodunuzda başlığı. Öğesinin içeriğini değiştirin `MyExecRefsLib.cpp` Bu kod ile:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]

1. Yürütülebilir dosya seçerek yapı **derleme** > **Çözümü Derle** menü çubuğunda.

##  <a name="RunApp"></a> Uygulamayı çalıştırma

### <a name="to-run-the-app"></a>Uygulamayı çalıştırmak için

1. Emin olun **MyExecRefsLib** için kısayol menüsünü açıp varsayılan proje olarak seçildiğinden **MyExecRefsLib** içinde **Çözüm Gezgini**ve ardından seçme **Başlangıç projesi olarak ayarla**.

1. Menü çubuğunda projeyi çalıştırmak için seçin **hata ayıklama** > **hata ayıklama olmadan Başlat**. Çıktıya benzemelidir:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[Masaüstü Uygulamaları (Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>

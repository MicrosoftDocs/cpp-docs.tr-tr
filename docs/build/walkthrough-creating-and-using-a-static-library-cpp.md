---
title: 'İzlenecek yol: Statik Kitaplık Oluşturma ve Kullanma (C++)'
description: Visual C++ Studio 'da bir statik kitaplık (. lib) oluşturmak için kullanın.
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.author: corob
ms.openlocfilehash: c81ccd970383c8571a7d0d1e77d4b8fe44900bcf
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078187"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>İzlenecek yol: Statik Kitaplık Oluşturma ve Kullanma (C++)

Bu adım adım izlenecek yol, C++ uygulamalarla kullanılmak üzere statik bir kitaplığın (. lib dosyası) nasıl oluşturulacağını gösterir. Statik kitaplık kullanmak, kodu yeniden kullanmak için harika bir yoldur. İşlevselliği gerektiren her uygulamada aynı yordamları yeniden uygulamak yerine, bunları statik bir kitaplığa bir kez yazar ve ardından uygulamalardan başvurar. Statik kitaplıktan bağlantılı kod uygulamanızın bir parçası haline gelir — kodu kullanmak için başka bir dosya yüklemek zorunda değilsiniz.

Bu izlenecek yol aşağıdaki görevleri içerir:

- [Statik kitaplık projesi oluşturma](#CreateLibProject)

- [Statik kitaplığa sınıf ekleme](#AddClassToLib)

- [Statik kitaplığa C++ başvuran bir konsol uygulaması oluşturma](#CreateAppToRefTheLib)

- [Uygulamadaki statik kitaplıktan işlevselliği kullanma](#UseLibInApp)

- [Uygulamayı çalıştırma](#RunApp)

## <a name="prerequisites"></a>Önkoşullar

C++ Dilin temellerini anlama.

##  <a name="creating-a-static-library-project"></a><a name="CreateLibProject"></a>Statik kitaplık projesi oluşturma

Projeyi oluşturma yönergeleri, Visual Studio 2019 veya önceki bir sürümünü kullanıp kullanmayacağınızı bağlı olarak farklılık gösterir. Bu sayfanın sol üst kısmında doğru sürüm kümesine sahip olduğunuzdan emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-static-library-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de statik kitaplık projesi oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda **dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **kitaplık**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **statik kitaplık** ' ı seçin ve ardından **İleri**' yi seçin. Bir sonraki sayfada, proje için bir ad belirtmek üzere **ad** kutusuna *MathFuncsLib* girin ve isterseniz proje konumunu belirtin.

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-static-library-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de statik kitaplık projesi oluşturmak için

1. Menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **C++görsel**' i genişletin ve ardından **Windows Masaüstü**' nü seçin. Orta bölmede **Windows Masaüstü Sihirbazı**' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MathFuncsLib*) belirtin. Çözüm **adı** kutusunda çözüm için bir ad (örneğin, *StaticLibrary*) belirtin. **Tamam** düğmesini seçin.

1. **Uygulama türü**altında, **statik kitaplık (. lib)** öğesini seçin.

1. **Ek seçenekler**altında, **önceden derlenmiş üstbilgiyi** kaldırın onay kutusunu işaretleyin.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-static-library-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de statik kitaplık projesi oluşturmak için

1. Menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **Visual C++**  >  > **Şablonlar** **' ı genişletin** ve ardından **Win32**' yi seçin. Orta bölmede **Win32 konsol uygulaması**' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MathFuncsLib*) belirtin. Çözüm **adı** kutusunda çözüm için bir ad (örneğin, *StaticLibrary*) belirtin. **Tamam** düğmesini seçin.

1. **İleri**’ye tıklayın.

1. **Uygulama türü**altında, **statik kitaplık**' ı seçin. Ardından **önceden derlenmiş üst bilgi** kutusunun işaretini kaldırın ve **son**' u seçin.

::: moniker-end

##  <a name="adding-a-class-to-the-static-library"></a><a name="AddClassToLib"></a>Statik kitaplığa sınıf ekleme

### <a name="to-add-a-class-to-the-static-library"></a>Statik kitaplığa bir sınıf eklemek için

1. Yeni bir sınıf için üst bilgi dosyası oluşturmak için **Çözüm Gezgini**' de **MathFuncsLib** projesinin kısayol menüsünü açın ve > **Yeni öğe** **Ekle** ' yi seçin. **Yeni öğe Ekle** iletişim kutusunda sol bölmedeki **C++görsel**altında **kod**' ı seçin. Orta bölmede **üst bilgi dosyası (. h)** öğesini seçin. Üstbilgi dosyası için bir ad belirtin — örneğin, *MathFuncsLib. h*— ve sonra **Ekle** düğmesini seçin. Boş bir üstbilgi dosyası görüntülenir.

1. Toplama, çıkarma, çarpma ve bölme gibi genel matematik işlemlerini yapmak için `MyMathFuncs` adlı bir sınıf ekleyin. Kod şöyle olmalıdır:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]

1. Yeni sınıf için bir kaynak dosyası oluşturmak için, **Çözüm Gezgini**içinde **MathFuncsLib** projesinin kısayol menüsünü açın ve sonra > **Yeni öğe** **Ekle** ' yi seçin. **Yeni öğe Ekle** iletişim kutusunda sol bölmedeki **C++görsel**altında **kod**' ı seçin. Orta bölmede  **C++ dosya (. cpp)** öğesini seçin. Kaynak dosya için bir ad belirtin — örneğin, *MathFuncsLib. cpp*— ve sonra **Ekle** düğmesini seçin. Boş bir kaynak dosyası görüntülenir.

1. **MyMathFuncs**için işlevselliği uygulamak üzere bu kaynak dosyayı kullanın. Kod şöyle olmalıdır:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]

1. Menü çubuğunda **build** > **Build Solution** öğesini seçerek statik kitaplığı derleyin. Derleme, diğer programlar tarafından kullanılabilen bir statik kitaplık oluşturur.

   > [!NOTE]
   > Visual Studio komut satırında oluşturduğunuzda, programı iki adımda derlemeniz gerekir. İlk olarak, kodu derlemek ve `MathFuncsLib.obj`adlı bir nesne dosyası oluşturmak için `cl /c /EHsc MathFuncsLib.cpp` çalıştırın. (`cl` komutu, CL. exe ' yi çağırır ve `/c` seçeneği bağlama olmadan derlemeyi belirtir. Daha fazla bilgi için bkz. [/c (bağlama olmadan Derle)](../build/reference/c-compile-without-linking.md).) İkinci olarak, kodu bağlamak ve statik kitaplık `MathFuncsLib.lib`oluşturmak için `lib MathFuncsLib.obj` çalıştırın. (`lib` komutu kitaplık Yöneticisi, lib. exe ' yi çağırır. Daha fazla bilgi için bkz. [LIB Reference](../build/reference/lib-reference.md).)

##  <a name="creating-a-c-console-app-that-references-the-static-library"></a><a name="CreateAppToRefTheLib"></a>Statik kitaplığa C++ başvuran bir konsol uygulaması oluşturma

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2019"></a>Visual Studio 2019 C++ ' de statik kitaplığa başvuran bir konsol uygulaması oluşturmak için

1. **Çözüm Gezgini**, çözüm için en üst düğüme sağ tıklayın ve yeni **Proje** Ekle iletişim kutusunu açmak Için > **Yeni proje** **Ekle** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Bir sonraki sayfada, proje için bir ad belirtmek ve isterseniz proje konumunu belirtmek için **ad** kutusuna *MyExecRefsLib* ' i girin.

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2017"></a>Visual Studio 2017 C++ ' de statik kitaplığa başvuran bir konsol uygulaması oluşturmak için

1. Menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunun sol bölmesinde, **yüklü** > **C++görsel**' i genişletin ve ardından **Windows Masaüstü**' nü seçin. Orta bölmede **Windows Masaüstü Sihirbazı**' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MyExecRefsLib*) belirtin. **Çözüm**' nün yanındaki aşağı açılan listede **çözüme Ekle**' yi seçin. Bu komut, yeni projeyi statik kitaplığı içeren çözüme ekler. **Tamam** düğmesini seçin.

1. **Uygulama türü**altında **konsol uygulaması (. exe)** öğesini seçin.

1. **Ek seçenekler**altında, **önceden derlenmiş üstbilgiyi** kaldırın onay kutusunu işaretleyin.

1. Projeyi oluşturmak için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2015"></a>Visual Studio 2015 C++ ' de statik kitaplığa başvuran bir konsol uygulaması oluşturmak için

1. Menü çubuğunda **dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **Visual C++**  >  > **Şablonlar** **' ı genişletin** ve ardından **Win32**' yi seçin. Orta bölmede **Win32 konsol uygulaması**' nı seçin.

1. **Ad** kutusuna proje için bir ad (örneğin, *MyExecRefsLib*) belirtin. **Çözüm**' nün yanındaki aşağı açılan listede **çözüme Ekle**' yi seçin. Bu komut, yeni projeyi statik kitaplığı içeren çözüme ekler. **Tamam** düğmesini seçin.

1. **İleri**’ye tıklayın.

1. **Konsol uygulamasının** seçili olduğundan emin olun. Ardından **boş proje** kutusunu Işaretleyin ve **son**' u seçin.

::: moniker-end

##  <a name="using-the-functionality-from-the-static-library-in-the-app"></a><a name="UseLibInApp"></a>Uygulamadaki statik kitaplıktan işlevselliği kullanma

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>Uygulamadaki statik kitaplıktan işlevselliği kullanmak için

1. Bir konsol uygulaması oluşturduktan sonra, sizin için boş bir program oluşturulur. Kaynak dosyanın adı, daha önce seçtiğiniz adla aynıdır. Örnekte, `MyExecRefsLib.cpp`olarak adlandırılmıştır.

1. Statik kitaplıkta matematik yordamlarını kullanabilmeniz için, buna başvurmanız gerekir. **Çözüm Gezgini**, **MyExecRefsLib** projesi için kısayol menüsünü açın ve sonra > **başvuru** **Ekle** ' yi seçin.

1. **Başvuru Ekle** iletişim kutusu, başvurekleyebileceğiniz kitaplıkları listeler. **Projeler** sekmesi geçerli çözümdeki projeleri ve bunların başvurdukları kitaplıkları listeler. **Projeler** sekmesinde, **MathFuncsLib** onay kutusunu işaretleyin ve ardından **Tamam** düğmesini seçin.

1. `MathFuncsLib.h` üst bilgi dosyasına başvurmak için, dahil edilen dizinlerin yolunu değiştirmeniz gerekir. **MyExecRefsLib**için **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri** düğümünü genişletin, **C/C++**  düğümünü genişletin ve ardından **genel**' i seçin. **Ek Içerme dizinleri**' nin yanında, **MathFuncsLib** dizininin yolunu belirtin veya buna gidin.

   Dizin yoluna gitmek için, özellik değeri açılan listesini açın ve ardından **Düzenle**' yi seçin. **Ek Içerik dizinleri** iletişim kutusunda, metin kutusunda boş bir satır seçin ve satırın sonundaki üç nokta düğmesini ( **...** ) seçin. **Dizin Seç** iletişim kutusunda, **MathFuncsLib** dizinini seçin ve sonra seçiminizi kaydetmek ve Iletişim kutusunu kapatmak için **Klasör Seç** düğmesini seçin. **Ek Içerik dizinleri** iletişim kutusunda, **Tamam** düğmesini seçin ve ardından **Özellik sayfaları** iletişim kutusunda, projedeki değişiklikleri kaydetmek için **Tamam** düğmesini seçin.

1. Artık kodunuzda `#include "MathFuncsLib.h"` üst bilgisini ekleyerek bu uygulamadaki `MyMathFuncs` sınıfını kullanabilirsiniz. `MyExecRefsLib.cpp` içeriğini şu kodla değiştirin:

   [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]

1. Menü çubuğunda **build** > **Build Solution** öğesini seçerek yürütülebilir dosya oluşturun.

##  <a name="running-the-app"></a><a name="RunApp"></a>Uygulamayı çalıştırma

### <a name="to-run-the-app"></a>Uygulamayı çalıştırmak için

1. **Çözüm Gezgini**, **MyExecRefsLib** için kısayol menüsünü açarak ve ardından **Başlangıç projesi olarak ayarla**' yı seçerek, **MyExecRefsLib** öğesinin varsayılan proje olarak seçildiğinden emin olun.

1. Projeyi çalıştırmak için, menü çubuğunda **hata ayıkla** > hata **ayıklama olmadan Başlat**' ı seçin. Çıktı şuna benzemelidir:

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[Masaüstü Uygulamaları (Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>

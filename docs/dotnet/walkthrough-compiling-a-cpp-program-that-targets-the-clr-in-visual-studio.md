---
title: CLR’yi Hedefleyen bir C++/CLI Programı Derleme
description: Yerel C++ kodu ve .NET programlarını bağlayabilirler program ve kitaplıklar oluşturmak için Microsoft C++ kullanın.
ms.date: 04/23/2019
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: d6d06104cc007ae5ff20f579225c885690a704e4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924215"
---
# <a name="walkthrough-compile-a-ccli-program-that-targets-the-clr-in-visual-studio"></a>İzlenecek yol: Visual Studio 'da CLR 'yi hedefleyen bir C++/CLı programını derleme

C++/CLı kullanarak, .NET sınıflarının yanı sıra yerel C++ türlerini kullanan C++ programları oluşturabilirsiniz. C++/CLı, konsol uygulamalarında ve yerel C++ kodunu sarın ve .NET programlarından erişilebilir hale gelen DLL 'lerde kullanılmak üzere tasarlanmıştır. .NET tabanlı bir Windows Kullanıcı arabirimi oluşturmak için C# veya Visual Basic kullanın.

Bu yordam için kendi C++ programınızı yazabilir veya örnek programlardan birini kullanabilirsiniz. Bu yordamda kullandığımız örnek program, textfile.txt adlı bir metin dosyası oluşturur ve proje dizinine kaydeder.

## <a name="prerequisites"></a>Önkoşullar

- C++ dilinin temellerini anlama.
- Visual Studio 2017 ve üzeri sürümlerde, C++/CLı desteği isteğe bağlı bir bileşendir. Yüklemek için, Windows Başlat menüsünden **Visual Studio yükleyicisi** açın. **C++ Ile masaüstü geliştirme** kutucuğunun seçili olduğundan emin olun ve **isteğe bağlı** bileşenler bölümünde **C++/CLI desteğini** de denetleyin.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma

Aşağıdaki adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="msvc-160"

### <a name="to-create-a-ccli-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir C++/CLı projesi oluşturmak için

1. **Çözüm Gezgini** ' de, en üste sağ tıklayıp **Yeni proje oluştur** iletişim kutusunu açın.

1. İletişim kutusunda **clr** yazın ve ardından sonuçlar listesinden **clr boş proje** ' yi seçin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="msvc-150"

### <a name="to-create-a-ccli-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir C++/CLı projesi oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde, **Yeni** ' nin üzerine gelin ve ardından **Proje** ' ye tıklayın.

1. Visual C++ proje türlerinden **clr** ' ye tıklayın ve ardından **clr boş proje** ' ye tıklayın.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm, yeni projeyle aynı ada sahiptir, ancak farklı bir ad girebilirsiniz. İsterseniz proje için farklı bir konum girebilirsiniz.

1. Yeni projeyi oluşturmak için **Tamam** ' ı tıklatın.

::: moniker-end

::: moniker range="msvc-140"

### <a name="to-create-a-ccli-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de bir C++/CLı projesi oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde, **Yeni** ' nin üzerine gelin ve ardından **Proje** ' ye tıklayın.

1. Visual C++ proje türlerinden **clr** ' ye tıklayın ve ardından **clr boş proje** ' ye tıklayın.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm, yeni projeyle aynı ada sahiptir, ancak farklı bir ad girebilirsiniz. İsterseniz proje için farklı bir konum girebilirsiniz.

1. Yeni projeyi oluşturmak için **Tamam** ' ı tıklatın.

::: moniker-end

## <a name="add-a-source-file"></a>Kaynak dosya Ekle

1. **Çözüm Gezgini** görünmüyorsa, **Görünüm** menüsünde **Çözüm Gezgini** ' a tıklayın.

1. Projeye yeni bir kaynak dosyası ekleyin:

   - **Çözüm Gezgini** ' de **kaynak dosyalar** klasörüne sağ tıklayın, **Ekle** ' nin üzerine gelin ve **Yeni öğe** ' ye tıklayın.

   - **C++ dosyası (. cpp)** seçeneğine tıklayın ve bir dosya adı yazın ve ardından **Ekle** ' ye tıklayın.

   **. Cpp** dosyası **Çözüm Gezgini** içindeki **kaynak dosyaları** klasöründe görünür ve bu dosyada istediğiniz kodu yazdığınız bir sekmeli pencere görüntülenir.

1. Visual Studio 'da yeni oluşturulan sekmesine tıklayın ve geçerli bir Visual C++ program yazın veya örnek programlardan birini kopyalayıp yapıştırın.

   Örneğin, [nasıl yapılır: metin dosyası yazma (C++/CLI)](./file-handling-and-i-o-cpp-cli.md#write_text) örnek programını kullanabilirsiniz (programlama kılavuzunun **Dosya işleme ve g/ç** düğümünde).

   Örnek programı kullanıyorsanız, **`gcnew`** **`new`** bir .net nesnesi oluştururken yerine anahtar sözcüğünü kullanacağınızı ve **`gcnew`** bir işaretçi () yerine bir tanıtıcı () döndürdüğünü unutmayın `^` `*` :

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   C++/CLı sözdizimi hakkında daha fazla bilgi için bkz. [çalışma zamanı platformları Için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

1. **Yapı** menüsünde **Yapı Çözümü** ’ne tıklayın.

   **Çıktı** penceresi, derleme günlüğü konumu ve derleme durumunu gösteren bir ileti gibi derleme ilerlemesi hakkındaki bilgileri görüntüler.

   Değişiklik yapıp programı bir derleme yapmadan çalıştırırsanız, bir iletişim kutusu projenin güncel olmadığını gösterebilir. Visual Studio 'nun uygulamayı her oluşturduğunda sormak yerine her zaman güncel dosya sürümlerini kullanmasını istiyorsanız **Tamam** ' a tıklayarak bu iletişim kutusunda onay kutusunu seçin.

1. **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat** ' a tıklayın.

1. Örnek programı kullandıysanız, programı çalıştırdığınızda, metin dosyasının oluşturulduğunu belirten bir komut penceresi görüntülenir.

   **textfile.txt** metin dosyası artık proje dizininizde bulunur. Bu dosyayı Not defteri 'Ni kullanarak açabilirsiniz.

   > [!NOTE]
   > Boş CLR proje şablonunu seçme, derleyici seçeneğini otomatik olarak ayarlar `/clr` . Bunu doğrulamak için **Çözüm Gezgini** ' de projeye sağ tıklayın ve **Özellikler** ' e tıkladıktan sonra **yapılandırma özellikleri** ' nin **genel** düğümünde **ortak dil çalışma zamanı desteği** seçeneğini işaretleyin.

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

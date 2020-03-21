---
title: CLR 'yi C++hedefleyen bir/CLI programını derleme
description: Yerel C++ kod C++ ve .net programlarını bağlayabilirler program ve kitaplıklar oluşturmak için Microsoft 'u kullanın.
ms.date: 04/23/2019
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 36c41856dfcdb5c5f50ba59205b4c73c5fde5963
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80080013"
---
# <a name="walkthrough-compile-a-ccli-program-that-targets-the-clr-in-visual-studio"></a>İzlenecek yol: Visual C++STUDIO 'da clr 'yi hedefleyen bir/CLI programını derleme

/CLI kullanarak C++, .net sınıflarının yanı C++ sıra yerel C++ türler kullanan programlar da oluşturabilirsiniz. C++/CLı, konsol uygulamalarında ve yerel C++ kodu kaydırmak ve .net programlarından erişilebilir hale getirmek Için kullanılan dll 'lerde kullanılmak üzere tasarlanmıştır. .NET tabanlı bir Windows Kullanıcı arabirimi oluşturmak için veya Visual Basic kullanın C# .

Bu yordam için kendi C++ programınızı yazabilir veya örnek programlardan birini kullanabilirsiniz. Bu yordamda kullandığımız örnek program, textfile. txt adlı bir metin dosyası oluşturur ve bunu proje dizinine kaydeder.

## <a name="prerequisites"></a>Önkoşullar

- C++ Dilin temellerini anlama.
- Visual Studio 2017 ve üzeri sürümlerde, C++/CLI desteği isteğe bağlı bir bileşendir. Yüklemek için, Windows Başlat menüsünden **Visual Studio yükleyicisi** açın. Kutucuk **ile C++ masaüstü geliştirme** 'nın işaretli olduğundan ve **isteğe bağlı** bileşenler bölümünde,  **C++/CLI desteğini**de denetleyin.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma

Aşağıdaki adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Bu sayfanın sol üst kısmındaki sürüm seçicinin doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-ccli-project-in-visual-studio-2019"></a>Visual Studio 2019 C++' de bir/CLI projesi oluşturmak için

1. **Çözüm Gezgini**' de, en üste sağ tıklayıp **Yeni proje oluştur** iletişim kutusunu açın.

1. İletişim kutusunda **clr** yazın ve ardından sonuçlar listesinden **clr boş proje** ' yi seçin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-ccli-project-in-visual-studio-2017"></a>Visual Studio 2017 C++' de bir/CLI projesi oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde, **Yeni**' nin üzerine gelin ve ardından **Proje**' ye tıklayın.

1. Görsel C++ proje türleri ' nden **clr**' ye ve ardından **clr boş proje**' ye tıklayın.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm, yeni projeyle aynı ada sahiptir, ancak farklı bir ad girebilirsiniz. İsterseniz proje için farklı bir konum girebilirsiniz.

1. Yeni projeyi oluşturmak için **Tamam** ' ı tıklatın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-ccli-project-in-visual-studio-2015"></a>Visual Studio 2015 C++' de bir/CLI projesi oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde, **Yeni**' nin üzerine gelin ve ardından **Proje**' ye tıklayın.

1. Görsel C++ proje türleri ' nden **clr**' ye ve ardından **clr boş proje**' ye tıklayın.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm, yeni projeyle aynı ada sahiptir, ancak farklı bir ad girebilirsiniz. İsterseniz proje için farklı bir konum girebilirsiniz.

1. Yeni projeyi oluşturmak için **Tamam** ' ı tıklatın.

::: moniker-end

## <a name="add-a-source-file"></a>Kaynak dosya Ekle

1. **Çözüm Gezgini** görünmüyorsa, **Görünüm** menüsünde **Çözüm Gezgini** ' a tıklayın.

1. Projeye yeni bir kaynak dosyası ekleyin:

   - **Çözüm Gezgini**' de **kaynak dosyalar** klasörüne sağ tıklayın, **Ekle**' nin üzerine gelin ve **Yeni öğe**' ye tıklayın.

   - **C++ Dosya (. cpp)** öğesine tıklayın ve bir dosya adı yazın ve ardından **Ekle**' ye tıklayın.

   **. Cpp** dosyası **Çözüm Gezgini** içindeki **kaynak dosyaları** klasöründe görünür ve bu dosyada istediğiniz kodu yazdığınız bir sekmeli pencere görüntülenir.

1. Visual Studio 'da yeni oluşturulan sekmesine tıklayın ve geçerli bir görsel C++ program yazın veya örnek programlardan birini kopyalayıp yapıştırın.

   Örneğin, [nasıl yapılır: metin dosyası yazma (C++/CLI)](how-to-write-a-text-file-cpp-cli.md) örnek programını kullanabilirsiniz (programlama kılavuzunun **Dosya işleme ve g/ç** düğümünde).

   Örnek programı kullanıyorsanız, bir .NET nesnesi oluştururken `new` yerine `gcnew` anahtar sözcüğünü kullanacağınızı ve `gcnew` işaretçi (`*`) yerine bir tanıtıcı (`^`) döndürdüğünü unutmayın:

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   /CLI sözdizimi hakkında C++daha fazla bilgi için bkz. [çalışma zamanı platformları için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

1. **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Çıktı** penceresi, derleme günlüğü konumu ve derleme durumunu gösteren bir ileti gibi derleme ilerlemesi hakkındaki bilgileri görüntüler.

   Değişiklik yapıp programı bir derleme yapmadan çalıştırırsanız, bir iletişim kutusu projenin güncel olmadığını gösterebilir. Visual Studio 'nun uygulamayı her oluşturduğunda sormak yerine her zaman güncel dosya sürümlerini kullanmasını istiyorsanız **Tamam** ' a tıklayarak bu iletişim kutusunda onay kutusunu seçin.

1. **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

1. Örnek programı kullandıysanız, programı çalıştırdığınızda, metin dosyasının oluşturulduğunu belirten bir komut penceresi görüntülenir.

   **Textfile. txt** metin dosyası artık proje dizininizde bulunur. Bu dosyayı Not defteri 'Ni kullanarak açabilirsiniz.

   > [!NOTE]
   > Boş CLR proje şablonunu seçme, `/clr` derleyici seçeneğini otomatik olarak ayarlar. Bunu doğrulamak için **Çözüm Gezgini** ' de projeye sağ tıklayın ve **Özellikler**' e tıkladıktan sonra **yapılandırma özellikleri**' nin **genel** düğümünde **ortak dil çalışma zamanı desteği** seçeneğini işaretleyin.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

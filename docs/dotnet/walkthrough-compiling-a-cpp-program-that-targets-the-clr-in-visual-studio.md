---
title: Derleme bir C++CLR'yi hedefleyen /CLI programı
description: Microsoft kullanım C++ programlar ve bağlanabilir kitaplıkları yerel oluşturmak için C++ kod ve .NET programlarının.
ms.date: 04/23/2019
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 8462b2b031bdcdebf65d58974c521d80e57d856d
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221813"
---
# <a name="walkthrough-compile-a-ccli-program-that-targets-the-clr-in-visual-studio"></a>İzlenecek yol: Derleme bir C++Visual Studio'da CLR'yi hedefleyen /CLI programı

Kullanarak C++/CLI oluşturabilirsiniz C++ yerel yanı sıra .NET sınıfları kullanan programlar C++ türleri. C++/ CLI konsol uygulamaları ve yerel kaydırma DLL'leri kullanılmak için tasarlanmıştır C++ kod ve .NET programlarının erişilebilir hale getirebilirsiniz. .NET tabanlı bir Windows kullanıcı arabirimi oluşturmak için kullanın C# veya Visual Basic. 

Bu yordam için kendi C++ programınızı yazabilir veya örnek programlardan birini kullanın. Bu yordamda kullandığımız örnek program, textfile.txt adlı bir metin dosyası oluşturur ve proje dizinine kaydeder.

## <a name="prerequisites"></a>Önkoşullar

- Bir C++ dilinin temellerini anlama.
- Visual Studio 2017 ve sonraki sürümlerinde, C++/CLI desteği isteğe bağlı bir bileşenidir. Yüklemek için açık **Visual Studio yükleyicisi** Windows Başlat menüsünde. Emin olun **ile masaüstü geliştirme C++**  kutucuk denetlenir ve **isteğe bağlı** bileşenleri bölüm, ayrıca onay  **C++CLI desteği**.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma

Aşağıdaki adımlar, kullandığınız Visual Studio'nun hangi sürümünün bağlı olarak farklılık gösterir. Bu sayfanın sol üst sürüm seçicisinde doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-ccli-project-in-visual-studio-2019"></a>Oluşturmak için bir C++Visual Studio 2019 /CLI projesinde

1. İçinde **Çözüm Gezgini**, açmak için ekranın üst sağ **yeni bir proje oluşturma** iletişim kutusu.

1. İletişim kutusunun üstüne yazın **CLR** arama kutusuna ve ardından **CLR boş proje** sonuçları listesinde. 

1. Seçin **Oluştur** projeyi oluşturmak için.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-ccli-project-in-visual-studio-2017"></a>Oluşturmak için bir C++/CLI proje Visual Studio 2017

1. Yeni bir proje oluşturun. Üzerinde **dosya** menüsünde **yeni**ve ardından **proje**.

1. Visual C++ proje türlerinden tıklayın **CLR**ve ardından **CLR boş proje**.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm yeni proje ile aynı ada sahiptir ancak farklı bir ad girebilirsiniz. İsterseniz, proje için farklı bir konum girebilirsiniz.

1. Tıklayın **Tamam** yeni projeyi oluşturmak için.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-ccli-project-in-visual-studio-2015"></a>Oluşturmak için bir C++/CLI proje Visual Studio 2015'te

1. Yeni bir proje oluşturun. Üzerinde **dosya** menüsünde **yeni**ve ardından **proje**.

1. Visual C++ proje türlerinden tıklayın **CLR**ve ardından **CLR boş proje**.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm yeni proje ile aynı ada sahiptir ancak farklı bir ad girebilirsiniz. İsterseniz, proje için farklı bir konum girebilirsiniz.

1. Tıklayın **Tamam** yeni projeyi oluşturmak için.

::: moniker-end

## <a name="add-a-source-file"></a>Bir kaynak dosyası ekleme

1. Varsa **Çözüm Gezgini** görünmeyen, tıklayın **Çözüm Gezgini** üzerinde **görünümü** menüsü.

1. Yeni bir kaynak dosyası projeye ekleyin:

   - Sağ **kaynak dosyaları** klasöründe **Çözüm Gezgini**, işaret **Ekle**, tıklatıp **yeni öğe**.

   - Tıklayın **C++ dosyası (.cpp)** ve bir dosya adı yazın ve ardından **Ekle**.

   **.Cpp** dosya görünür **kaynak dosyaları** klasöründe **Çözüm Gezgini** ve kod girebileceğiniz bir sekmeli pencere görünür, bu dosyada istediğiniz.

1. Visual Studio'da yeni oluşturulan sekmesine tıklayın ve geçerli bir Visual C++ programı yazın veya kopyalayın ve örnek programlardan birini yapıştırın.

   Örneğin, kullanabileceğiniz [nasıl yapılır: Metin dosyaları yazma (C++/CLI)](how-to-write-a-text-file-cpp-cli.md) örnek program (içinde **dosya işleme ve g/ç** düğümünün Programlama Kılavuzu).

   Örnek programı kullanırsanız, kullandığına dikkat edin `gcnew` anahtar sözcüğü yerine `new` bir .NET nesnesini ve oluştururken `gcnew` bir tanıtıcı döndürür (`^`) yerine bir işaretçi (`*`):

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   Daha fazla bilgi için C++/CLI sözdizimine bakın [çalışma zamanı platformları için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

1. Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   **Çıkış** pencere konumunu yapı günlüğüne ve yapı durumunu belirten bir ileti gibi derleme ilerlemesi hakkında bilgileri görüntüler.

   Değişiklik yapmak ve bir yapı yapmadan programı çalıştırırsanız, bir iletişim kutusu projenin güncel olduğunu gösterebilir. Tıklamadan önce bu iletişim kutusundaki onay kutusunu işaretleyin **Tamam** dosyaları güncel sürümleri yerine her zaman sormadan kullanılması her zaman Visual Studio istiyorsanız, uygulama oluşturur.

1. Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

1. Programı çalıştırdığınızda örnek programı kullandıysanız bir metin dosyasının oluşturulduğunu belirten bir komut penceresi görüntülenir.

   **Textfile.txt** metin dosyası artık proje dizininde bulunur. Not Defteri'ni kullanarak bu dosyayı açabilirsiniz.

   > [!NOTE]
   > Boş CLR seçerek proje şablonu otomatik olarak `/clr` derleyici seçeneği. Bunu doğrulamak için projeye sağ **Çözüm Gezgini** tıklayıp **özellikleri**, iade edin **ortak dil çalışma zamanı desteği** seçeneği **Genel** düğümünün **yapılandırma özellikleri**.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

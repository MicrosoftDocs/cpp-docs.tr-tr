---
title: CLR’yi Hedefleyen bir C++/CLI Programı Derleme
description: Yerel C++ kodu ve .NET programlarını bağlayabilen programlar ve kitaplıklar oluşturmak için Microsoft C++ kullanın.
ms.date: 04/23/2019
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 0d661d9e77211a0e49f8695ad713b607377a236a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371805"
---
# <a name="walkthrough-compile-a-ccli-program-that-targets-the-clr-in-visual-studio"></a>Walkthrough: Visual Studio'da CLR'yi Hedefleyen Bir C++/CLI Programı Derleme

C++/CLI kullanarak .NET sınıflarını ve yerel C++ türlerini kullanan C++ programları oluşturabilirsiniz. C++/CLI, konsol uygulamalarında ve yerel C++ kodunu saran ve .NET programlarından erişilebilir hale getiren DL'lerde kullanılmak üzere tasarlanmıştır. .NET tabanlı bir Windows kullanıcı arabirimi oluşturmak için C# veya Visual Basic kullanın.

Bu yordam için kendi C++ programınızı yazabilir veya örnek programlardan birini kullanabilirsiniz. Bu yordamda kullandığımız örnek program textfile.txt adlı bir metin dosyası oluşturur ve proje dizinine kaydeder.

## <a name="prerequisites"></a>Ön koşullar

- C++ dilinin temellerinin anlaşılması.
- Visual Studio 2017 ve sonrası durumlarda C++/CLI desteği isteğe bağlı bir bileşendir. Yüklemek için Windows Başlat menüsünden **Visual Studio Yükleyici'yi** açın. **C++ döşemesi içeren Masaüstü geliştirmenin** denetlendirildiğinden emin olun ve **İsteğe Bağlı** bileşenler bölümünde **C++/CLI Desteği'ni**de kontrol edin.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma

Aşağıdaki adımlar Visual Studio'nun hangi sürümünü kullandığınıza bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-ccli-project-in-visual-studio-2019"></a>Visual Studio 2019'da C++/CLI projesi oluşturmak için

1. **Çözüm Gezgini'nde,** **Yeni Proje Oluştur** iletişim kutusunu açmak için en üste sağ tıklayın.

1. İletişim kutusunun üst kısmında, arama kutusuna **CLR** yazın ve ardından sonuçlar listesinden **CLR Boş Proje'yi** seçin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-ccli-project-in-visual-studio-2017"></a>Visual Studio 2017'de C++/CLI projesi oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde **Yeni'yi**işaret edin ve ardından **Project'i**tıklatın.

1. Visual C++ proje türlerinden **CLR'yi**tıklatın ve ardından **CLR Boş Proje'yi**tıklatın.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm yeni projeyle aynı ada sahiptir, ancak farklı bir ad girebilirsiniz. İsterseniz proje için farklı bir konum girebilirsiniz.

1. Yeni projeyi oluşturmak için **Tamam'ı** tıklatın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-ccli-project-in-visual-studio-2015"></a>Visual Studio 2015'te C++/CLI projesi oluşturmak için

1. Yeni bir proje oluşturma. **Dosya** menüsünde **Yeni'yi**işaret edin ve ardından **Project'i**tıklatın.

1. Visual C++ proje türlerinden **CLR'yi**tıklatın ve ardından **CLR Boş Proje'yi**tıklatın.

1. Bir proje adı yazın. Varsayılan olarak, projeyi içeren çözüm yeni projeyle aynı ada sahiptir, ancak farklı bir ad girebilirsiniz. İsterseniz proje için farklı bir konum girebilirsiniz.

1. Yeni projeyi oluşturmak için **Tamam'ı** tıklatın.

::: moniker-end

## <a name="add-a-source-file"></a>Kaynak dosya ekleme

1. **Çözüm Gezgini** görünmüyorsa, **Görünüm** menüsünde **Çözüm Gezgini'ni** tıklatın.

1. Projeye yeni bir kaynak dosyası ekleyin:

   - **Çözüm Gezgini'ndeki** **Kaynak Dosyalar** klasörüne sağ tıklayın, **Ekle'ye**işaret edin ve **Yeni Öğe'yi**tıklatın.

   - **C++ Dosyası'nı (.cpp)** tıklatın ve bir dosya adı yazın ve sonra **Ekle'yi**tıklatın.

   **.cpp** dosyası **Solution Explorer'daki** **Kaynak Dosyalar** klasöründe görünür ve bu dosyaya istediğiniz kodu yazdığınız sekmeli bir pencere görüntülenir.

1. Visual Studio'da yeni oluşturulan sekmede tıklayın ve geçerli bir Visual C++ programı yazın veya örnek programlardan birini kopyalayıp yapıştırın.

   Örneğin, [Nasıl Yazılır: Metin Dosyası Yazma (C++/CLI)](how-to-write-a-text-file-cpp-cli.md) örnek programı (Programlama Kılavuzu'nun **Dosya İşleme ve I/İş** düğümünde) kullanabilirsiniz.

   Örnek programı kullanıyorsanız, bir .NET `gcnew` nesnesi `new` oluştururken anahtar kelime yerine `gcnew` kullandığınızı`^`ve işaretçi yerine`*`bir tanıtıcı ( ) döndürür ( ):

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   C++/CLI sözdizimi hakkında daha fazla bilgi için [Çalışma Zamanı Platformları için Bileşen Uzantıları'na](../extensions/component-extensions-for-runtime-platforms.md)bakın.

1. **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Çıktı** penceresi, yapı günlüğünün konumu ve yapı durumunu gösteren bir ileti gibi derleme ilerlemesi yle ilgili bilgileri görüntüler.

   Değişiklik yapar ve programı oluşturma yapmadan çalıştırın, bir iletişim kutusu projenin güncel olmadığını gösterebilir. Visual Studio'nun uygulamayı her oluşturduğunda sizi istemek yerine dosyaların geçerli sürümlerini her zaman kullanmasını istiyorsanız **Tamam'ı** tıklatmadan önce bu iletişim kutusundaki onay kutusunu seçin.

1. Hata **Ayıklama** menüsünde Hata **Ayıklama olmadan Başlat'ı**tıklatın.

1. Örnek programı kullandıysanız, programı çalıştırdığınızda metin dosyasının oluşturulduğunu gösteren bir komut penceresi görüntülenir.

   **textfile.txt** metin dosyası artık proje dizininizde bulunmaktadır. Bu dosyayı Notepad'i kullanarak açabilirsiniz.

   > [!NOTE]
   > Boş CLR proje şablonunu seçmek `/clr` derleyici seçeneğini otomatik olarak ayarlar. Bunu doğrulamak **için, Solution Explorer'da** projeyi sağ tıklatın ve **Özellikler'i**tıklatın ve ardından Yapılandırma **Özellikleri'nin Genel** düğümünde **Ortak Dil Çalışma Zamanı destek** seçeneğini işaretleyin. **Configuration Properties**

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[Projeler ve yapı sistemleri](../build/projects-and-build-systems-cpp.md)<br/>

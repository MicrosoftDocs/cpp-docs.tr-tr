---
title: 'İzlenecek yol: Standart C++ Programı Oluşturma'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: 105ac62131b45afdea2a445b5888a344f1e4d46c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370223"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: Standart C++ Programı Oluşturma

Standart C++ programları oluşturmak için Visual Studio'yı kullanabilirsiniz. Bu izbin adımlarını izleyerek bir proje oluşturabilir, projeye yeni bir dosya ekleyebilir, C++ kodu eklemek için dosyayı değiştirebilir ve ardından Visual Studio'yu kullanarak programı derleyip çalıştırabilirsiniz.

Kendi C++ programınızı yazabilir veya örnek programlardan birini kullanabilirsiniz. Bu izbeden örnek program bir konsol uygulamasıdır. Bu uygulama, `set` C++ Standart Kitaplığı'ndaki kapsayıcıyı kullanır.

> [!NOTE]
> C++ dil standardının belirli bir sürümüyle uyumluluk gerekiyorsa (c++14 veya C++17) `/std:c++14` `/std:c++17` veya derleyici seçeneğini kullanın. (Visual Studio 2017 ve sonrası.)

## <a name="prerequisites"></a>Ön koşullar

Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.

### <a name="to-create-a-project-and-add-a-source-file"></a>Proje oluşturmak ve kaynak dosya eklemek için

Aşağıdaki adımlar Visual Studio'nun hangi sürümünü kullandığınıza bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>Visual Studio 2019'da C++ projesi oluşturmak için

1. Ana menüden, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **Konsol'a**ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Konsol Uygulaması'nı** seçin ve **ardından İleri'yi**seçin. Sonraki sayfada, proje için bir ad girin ve istenirse proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>Visual Studio 2017'de C++ projesi oluşturmak için

1. **Dosya** menüsünde **Yeni'yi** işaret ederek ve ardından **Project'i**tıklatarak proje oluşturun.

1. Visual **C++** proje türleri bölmesinde **Windows Desktop'ı**tıklatın ve ardından **Windows Console Application'ı**tıklatın.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm projeyle aynı ada sahiptir, ancak farklı bir ad yazabilirsiniz. Proje için farklı bir konum da yazabilirsiniz.

1. Projeyi oluşturmak için **Tamam**'a tıklayın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>Visual Studio 2015'te bir C++ projesi oluşturmak için

1. **Dosya** menüsünde **Yeni'yi** işaret ederek ve ardından **Project'i**tıklatarak proje oluşturun.

1. Visual **C++** proje türleri bölmesinde **Windows Desktop'ı**tıklatın ve ardından **Windows Console Application'ı**tıklatın.

1. Yeni **Proje** iletişim kutusunda, **Yüklü** > **Şablonlar** > **Görsel C++** genişletmek ve sonra **Win32**seçin. Orta bölmede **Win32 Konsol Uygulaması'nı**seçin.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm projeyle aynı ada sahiptir, ancak farklı bir ad yazabilirsiniz. Proje için farklı bir konum da yazabilirsiniz.

1. Projeyi oluşturmak için **Tamam**'a tıklayın.

1. **Win32 Uygulama Sihirbazı'nı**tamamlayın.

1. **İleri'yi**tıklatın, ardından **Konsol Uygulaması'nın** seçildiğinden emin olun ve **Önceden Derlenmiş Üstbilgi** kutusunun işaretlerini kaldırın.

1. **Son**'a tıklayın.

::: moniker-end

## <a name="add-a-new-source-file"></a>Yeni bir kaynak dosya ekleme

1. **Çözüm Gezgini** görüntülenmiyorsa, **Görünüm** menüsünde **Çözüm Gezgini'ni**tıklatın.

1. Projeye aşağıdaki gibi yeni bir kaynak dosyası ekleyin.

   1. **Çözüm Gezgini'nde,** **Kaynak Dosyalar** klasörüne sağ tıklayın, **Ekle'ye**işaret edin ve ardından **Yeni Öğe'yi**tıklatın.

   1. **Kod** düğümünde **C++ Dosyası'nı (.cpp)** tıklatın, dosya için bir ad yazın ve sonra **Ekle'yi**tıklatın.

   .cpp dosyası **Solution Explorer'daki** **Kaynak Dosyalar** klasöründe görünür ve dosya Visual Studio düzenleyicisinde açılır.

1. Düzenleyicideki dosyada, C++ Standart Kitaplığı kullanan geçerli bir C++ programı yazın veya örnek programlardan birini kopyalayıp dosyaya yapıştırın.

1. Dosyayı kaydedin.

1. **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Çıktı** penceresi, derleme ilerlemesi, örneğin yapı günlüğünün konumu ve yapı durumunu gösteren bir ileti yle ilgili bilgileri görüntüler.

1. Hata **Ayıklama** menüsünde Hata **Ayıklama olmadan Başlat'ı**tıklatın.

   Örnek programı kullandıysanız, bir komut penceresi görüntülenir ve kümede belirli tamsaların bulunup bulunmadığını gösterir.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [Visual C++ Konsol Uygulamaları](../windows/console-applications-in-visual-cpp.md)<br/>
**Sonraki:** [Walkthrough: Komut Satırında Yerel C++ Programı Derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplık](../standard-library/cpp-standard-library-reference.md)

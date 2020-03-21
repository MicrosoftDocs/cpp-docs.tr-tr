---
title: 'İzlenecek yol: standart C++ program oluşturma (C++)'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: 381fa347a4ca2872ef0697d76a1e788c97e8a014
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075434"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: standart C++ program oluşturma (C++)

Standart C++ programlar oluşturmak Için Visual Studio 'yu kullanabilirsiniz. Bu izlenecek adımları izleyerek bir proje oluşturabilir, projeye yeni bir dosya ekleyebilir, kod eklemek C++ için dosyayı değiştirebilir ve sonra Visual Studio 'yu kullanarak programı derleyip çalıştırabilirsiniz.

Kendi C++ programınızı yazabilir veya örnek programlardan birini kullanabilirsiniz. Bu izlenecek yolda örnek program bir konsol uygulamasıdır. Bu uygulama, C++ standart kitaplıktaki `set` kapsayıcısını kullanır.

> [!NOTE]
> C++ Dil standardının belirli bir sürümüyle uyumluluk (örn. c++ 14 veya c++ 17) gerekliyse, `/std:c++14` veya `/std:c++17` derleyici seçeneğini kullanın. (Visual Studio 2017 ve üzeri.)

## <a name="prerequisites"></a>Önkoşullar

Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.

### <a name="to-create-a-project-and-add-a-source-file"></a>Bir proje oluşturmak ve kaynak dosya eklemek için

Aşağıdaki adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Bu sayfanın sol üst kısmındaki sürüm seçicinin doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>Visual Studio 2019 C++ ' de bir proje oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden **dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, proje için bir ad girin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>Visual Studio 2017 C++ ' de bir proje oluşturmak için

1. **Dosya** menüsünde **Yeni** ' ye Işaret ederek ve ardından **Proje**' ye tıklayarak bir proje oluşturun.

1. **C++ Visual** Project Types bölmesinde **Windows Desktop**' a ve ardından **Windows konsol uygulaması**' na tıklayın.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir, ancak farklı bir ad yazabilirsiniz. Ayrıca, proje için farklı bir konum da yazabilirsiniz.

1. Projeyi oluşturmak için **Tamam**'a tıklayın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>Visual Studio 2015 C++ ' de bir proje oluşturmak için

1. **Dosya** menüsünde **Yeni** ' ye Işaret ederek ve ardından **Proje**' ye tıklayarak bir proje oluşturun.

1. **C++ Visual** Project Types bölmesinde **Windows Desktop**' a ve ardından **Windows konsol uygulaması**' na tıklayın.

1. **Yeni proje** iletişim kutusunda, **Visual C++**  >  > **Şablonlar** **' ı genişletin** ve ardından **Win32**' yi seçin. Orta bölmede **Win32 konsol uygulaması**' nı seçin.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir, ancak farklı bir ad yazabilirsiniz. Ayrıca, proje için farklı bir konum da yazabilirsiniz.

1. Projeyi oluşturmak için **Tamam**'a tıklayın.

1. **Win32 uygulama Sihirbazı 'nı**doldurun.

1. **İleri**' ye tıklayın, ardından **konsol uygulamasının** seçili olduğundan emin olun ve **önceden derlenmiş üstbilgiler** kutusunun işaretini kaldırın.

1. **Son**'a tıklayın.

::: moniker-end

## <a name="add-a-new-source-file"></a>Yeni bir kaynak dosya ekleyin

1. **Çözüm Gezgini** görüntülenmiyorsa, **Görünüm** menüsünde **Çözüm Gezgini**' a tıklayın.

1. Projeye aşağıdaki gibi yeni bir kaynak dosya ekleyin.

   1. **Çözüm Gezgini**, **kaynak dosyalar** klasörüne sağ tıklayın, **Ekle**' nin üzerine gelin ve ardından **Yeni öğe**' ye tıklayın.

   1. **Kod** düğümünde  **C++ dosya (. cpp)** öğesine tıklayın, dosya için bir ad yazın ve ardından **Ekle**' ye tıklayın.

   . Cpp dosyası **Çözüm Gezgini**Içindeki **kaynak dosyaları** klasöründe görünür ve dosya Visual Studio Düzenleyicisi 'nde açılır.

1. Düzenleyicideki dosyada, C++ C++ standart kitaplığı kullanan geçerli bir program yazın veya örnek programlardan birini kopyalayıp dosyaya yapıştırın.

1. Dosyayı kaydedin.

1. **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Çıkış** penceresi, derleme ilerlemesi hakkındaki bilgileri, örneğin, derleme günlüğünün konumunu ve yapı durumunu gösteren bir iletiyi görüntüler.

1. **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Örnek programı kullandıysanız, bir komut penceresi görüntülenir ve küme içinde belirli tamsayılar bulunup bulunamamadığını gösterir.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [Visual C++ 'teki konsol uygulamaları](../windows/console-applications-in-visual-cpp.md)<br/>
**Sonraki:** [Izlenecek yol: komut satırında C++ yerel bir program derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)

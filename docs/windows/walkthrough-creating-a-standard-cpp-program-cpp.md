---
title: 'İzlenecek yol: Standart C++ Programı Oluşturma'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: bf2a3fac92b756b395eda236ed4968608319823c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509616"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: Standart C++ Programı Oluşturma

Standart C++ programları oluşturmak için Visual Studio 'Yu kullanabilirsiniz. Bu izlenecek adımları izleyerek bir proje oluşturabilir, projeye yeni bir dosya ekleyebilir, C++ kodu eklemek için dosyayı değiştirebilir ve sonra Visual Studio 'Yu kullanarak programı derleyip çalıştırabilirsiniz.

Kendi C++ programınızı yazabilir veya örnek programlardan birini kullanabilirsiniz. Bu izlenecek yolda örnek program bir konsol uygulamasıdır. Bu uygulama, `set` C++ standart kitaplığı 'ndaki kapsayıcıyı kullanır.

> [!NOTE]
> C++ dil standardının (yani, C++ 14 veya C++ 17) belirli bir sürümüyle uyumluluk gerekliyse, `/std:c++14` veya `/std:c++17` derleyici seçeneğini kullanın. (Visual Studio 2017 ve üzeri.)

## <a name="prerequisites"></a>Önkoşullar

Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.

### <a name="to-create-a-project-and-add-a-source-file"></a>Bir proje oluşturmak ve kaynak dosya eklemek için

Aşağıdaki adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir C++ projesi oluşturmak için

1. **File** > **New** > **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında,  **dili** **C++** olarak ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, proje için bir ad girin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir C++ projesi oluşturmak için

1. **Dosya** menüsünde **Yeni** ' ye Işaret ederek ve ardından **Proje**' ye tıklayarak bir proje oluşturun.

1. **Visual C++** proje türleri bölmesinde, **Windows Masaüstü**' ne ve ardından **Windows konsol uygulaması**' na tıklayın.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir, ancak farklı bir ad yazabilirsiniz. Ayrıca, proje için farklı bir konum da yazabilirsiniz.

1. Projeyi oluşturmak için **Tamam**'a tıklayın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de bir C++ projesi oluşturmak için

1. **Dosya** menüsünde **Yeni** ' ye Işaret ederek ve ardından **Proje**' ye tıklayarak bir proje oluşturun.

1. **Visual C++** proje türleri bölmesinde, **Windows Masaüstü**' ne ve ardından **Windows konsol uygulaması**' na tıklayın.

1. **Yeni proje** iletişim kutusunda Visual C++ **yüklü**  >  **Şablonlar**  >  **Visual C++**' ı genişletin ve ardından **Win32**' yi seçin. Orta bölmede **Win32 konsol uygulaması**' nı seçin.

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

   1. **Kod** düğümünde **C++ dosyası (. cpp)**' na tıklayın, dosya için bir ad yazın ve ardından **Ekle**' ye tıklayın.

   . Cpp dosyası **Çözüm Gezgini**Içindeki **kaynak dosyaları** klasöründe görünür ve dosya Visual Studio Düzenleyicisi 'nde açılır.

1. Düzenleyicideki dosyada, C++ standart kitaplığını kullanan geçerli bir C++ programı yazın veya örnek programlardan birini kopyalayıp dosyaya yapıştırın.

1. Dosyayı kaydedin.

1. **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Çıkış** penceresi, derleme ilerlemesi hakkındaki bilgileri, örneğin, derleme günlüğünün konumunu ve yapı durumunu gösteren bir iletiyi görüntüler.

1. **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Örnek programı kullandıysanız, bir komut penceresi görüntülenir ve küme içinde belirli tamsayılar bulunup bulunamamadığını gösterir.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [Visual C++ içindeki konsol uygulamaları](./overview-of-windows-programming-in-cpp.md)<br/>
**Next:** [Izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)

---
title: 'İzlenecek yol: Standart bir C++ programını (C++) oluşturma'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: ed9c19dad029f8fc9495d38ab6e5c0ba8ad6d529
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877412"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: Standart bir C++ programını (C++) oluşturma

Visual Studio standart oluşturmak için kullanabileceğiniz C++ programlar. Bu kılavuzda açıklanan adımları izleyerek, bir proje oluşturun, projeye yeni bir dosya ekleyin, yapabilirsiniz C++ kodu eklemek ve ardından derleyin ve Visual Studio kullanarak programı çalıştırmak için dosyasını değiştirin.

Kendi C++ programınızı yazabilir veya örnek programlardan birini kullanın. Bu kılavuzda örnek program bir konsol uygulamasıdır. Bu uygulamanın kullandığı `set` C++ Standart Kitaplığı'nda kapsayıcı.

> [!NOTE]
> Belirli bir sürümü ile uyumluluk C++ dil standardı (yani C ++ 14 veya C ++ 17) gerekli, kullanın `/std:C++14` veya `/std:c++17` derleyici seçeneği. (Visual Studio 2017 ve üzeri.)

## <a name="prerequisites"></a>Önkoşullar

Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.

### <a name="to-create-a-project-and-add-a-source-file"></a>Bir proje oluşturun ve bir kaynak dosyası eklemek için

Aşağıdaki adımlar, kullandığınız Visual Studio'nun hangi sürümünün bağlı olarak farklılık gösterir. Bu sayfanın sol üst sürüm seçicisinde doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>Oluşturmak için bir C++ Visual Studio 2019 projesinde

1. Ana menüden **dosya** > **yeni** > **proje** açmak için **yeni bir proje oluşturma** iletişim bir kutu.

1. İletişim kutusunun üstündeki ayarlamak **dil** için **C++** ayarlayın **Platform** için **Windows**, ayarlayıp **proje türü** için **konsol**. 

1. Filtrelenmiş proje türleri listesinden seçim **konsol uygulaması** ardından **sonraki**. Sonraki sayfada, proje için bir ad girin ve istenen proje konumu belirtin.

1. Seçin **Oluştur** projeyi oluşturmak için.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>Oluşturmak için bir C++ proje Visual Studio 2017

1. İşaret ederek bir proje oluşturma **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.

1. İçinde **Visual C++** Proje Türleri bölmesinde ye **Windows Masaüstü**ve ardından **Windows konsol uygulaması**.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir ancak farklı bir ad yazabilirsiniz. Proje için farklı bir konum da yazabilirsiniz.

1. Tıklayın **Tamam** projeyi oluşturmak için.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>Oluşturmak için bir C++ proje Visual Studio 2015'te

1. İşaret ederek bir proje oluşturma **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.

1. İçinde **Visual C++** Proje Türleri bölmesinde ye **Windows Masaüstü**ve ardından **Windows konsol uygulaması**.

1. İçinde **yeni proje** iletişim kutusunda **yüklü** > **şablonları** > **Visual C++** , ve ardından **Win32**. Orta bölmede seçin **Win32 konsol uygulaması**.

1. Proje için bir ad yazın. Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir ancak farklı bir ad yazabilirsiniz. Proje için farklı bir konum da yazabilirsiniz.

1. Tıklayın **Tamam** projeyi oluşturmak için.

1. Tamamlamak **Win32 Uygulama Sihirbazı**. 

1. Tıklayın **sonraki**, ardından emin **konsol uygulaması** seçilidir ve işaretini kaldırın **önceden derlenmiş üst bilgiler** kutusu. 

1. **Son**'a tıklayın.

::: moniker-end

## <a name="add-a-new-source-file"></a>Yeni bir kaynak dosyası ekleme

1. Varsa **Çözüm Gezgini** , üzerinde görüntülenmediğini **görünümü** menüsünde tıklayın **Çözüm Gezgini**.

1. Yeni bir kaynak dosyası projeye aşağıdaki şekilde ekleyin.

   1. İçinde **Çözüm Gezgini**, sağ **kaynak dosyaları** klasörünü **Ekle**ve ardından **yeni öğe**.

   1. İçinde **kod** düğümünü tıklatın **C++ dosyası (.cpp)** dosyası için bir ad yazın ve ardından **Ekle**.

   .Cpp dosyası görünür **kaynak dosyaları** klasöründe **Çözüm Gezgini**, ve dosya Visual Studio Düzenleyicisi'nde açılır.

1. Düzenleyicideki dosyada, C++ Standart Kitaplığı'nı kullanan geçerli bir C++ programınızı yazabilir veya örnek programlardan birini kopyalayın ve dosyaya yapıştırın.

1. Dosyayı kaydedin.

1. Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   **Çıkış** penceresi, örneğin, konumunu yapı günlüğüne ve yapı durumunu belirten bir ileti gibi derleme ilerlemesi hakkında bilgileri görüntüler.

1. Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

   Örnek programı kullandıysanız bir komut penceresi görüntülenir ve kümede belirli tamsayılar bulunup bulunmadığını gösterir.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [Visual C++'ta Konsol Uygulamaları](../windows/console-applications-in-visual-cpp.md)<br/>
**Sonraki:** [İzlenecek yol: Komut Satırında Yerel C++ Programı Derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>

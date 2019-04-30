---
title: 'İzlenecek yol: Standart bir C++ programını (C++) oluşturma'
ms.custom: get-started-article
ms.date: 09/18/2018
f1_keywords:
- vcfirstapp
- vccreatefirst
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: d58d23e757a97402985ef60badf551523c0a275e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387805"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>İzlenecek yol: Standart bir C++ programını (C++) oluşturma

Standart C++ programlar oluşturmak için Visual Studio tümleşik geliştirme ortamında (IDE) Visual C++ kullanabilirsiniz. Bu kılavuzda açıklanan adımları izleyerek, bir proje oluşturun, projeye yeni bir dosya ekleyin, yapabilirsiniz C++ kodu eklemek ve ardından derleyin ve Visual Studio kullanarak programı çalıştırmak için dosyasını değiştirin.

Kendi C++ programınızı yazabilir veya örnek programlardan birini kullanın. Bu kılavuzda örnek program bir konsol uygulamasıdır. Bu uygulamanın kullandığı `set` C++ Standart Kitaplığı'nda kapsayıcı.

Visual C++ 2003 C++ standardı ile şu büyük özel durumlar aşağıdaki: iki aşamalı ad arama, özel durum belirtimleri ve dışarı aktarma. Ayrıca, görsel C++ örnek, lambda ifadeleri, otomatik, static_assert, rvalue başvuruları ve extern şablonları için birkaç C ++ 0 x özelliğini destekler.

> [!NOTE]
> Standart ile uyumluluk gerekliyse kullanın `/Za` Microsoft uzantılarını standart devre dışı bırakma derleyici seçeneği. Daha fazla bilgi için [/Za, /Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md).

## <a name="prerequisites"></a>Önkoşullar

Bu adım adım öğreticiyi tamamlamak için C++ dilinin temellerini anlamanız gerekir.

### <a name="to-create-a-project-and-add-a-source-file"></a>Bir proje oluşturun ve bir kaynak dosyası eklemek için

1. İşaret ederek bir proje oluşturma **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.

1. İçinde **Visual C++** Proje Türleri bölmesinde ye **Windows Masaüstü**ve ardından **Windows konsol uygulaması**.

   > [!NOTE]
   > Visual Studio 2017'den daha eski sürümleri için de **yeni proje** iletişim kutusunda **yüklü** > **şablonları**  >  **Visual C++** ve ardından **Win32**. Orta bölmede seçin **Win32 konsol uygulaması**.

   Proje için bir ad yazın.

   Varsayılan olarak, projeyi içeren çözüm proje ile aynı ada sahiptir ancak farklı bir ad yazabilirsiniz. Proje için farklı bir konum da yazabilirsiniz.

   Tıklayın **Tamam** projeyi oluşturmak için.

   > [!NOTE]
   > Visual Studio 2017'den daha eski sürümleri tamamlamak **Win32 Uygulama Sihirbazı**. Tıklayın **sonraki**, ardından emin **konsol uygulaması** seçilidir ve işaretini kaldırın **önceden derlenmiş üst bilgiler** kutusu. **Son**'a tıklayın.

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

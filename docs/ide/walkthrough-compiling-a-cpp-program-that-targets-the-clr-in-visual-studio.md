---
title: CLR'yi hedefleyen C++ programını derleme
ms.date: 09/17/2018
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 51e8b234792dea8dd7d61e4ac4b97a55bd5ea4e9
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524637"
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>İzlenecek Yol: Visual Studio'da CLR'yi Hedefleyen C++ Programını Derleme

.NET sınıflarını kullanın ve bunları Visual Studio geliştirme ortamını kullanarak derlemek için Visual C++ programlar oluşturabilirsiniz.

Bu yordam için kendi Visual C++ programınızı yazabilir veya örnek programlardan birini kullanın. Bu yordamda kullandığımız örnek program, textfile.txt adlı bir metin dosyası oluşturur ve proje dizinine kaydeder.

## <a name="prerequisites"></a>Önkoşullar

Bu konular, C++ dili temellerini anladığınızı varsayar.

### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Visual Studio'da yeni bir proje oluşturun ve yeni bir kaynak dosyası eklemek için

1. Yeni bir proje oluşturun. Üzerinde **dosya** menüsünde **yeni**ve ardından **proje**.

1. Visual C++ proje türlerinden tıklayın **CLR**ve ardından **CLR boş proje**.

   > [!NOTE]
   > Varsa **CLR boş proje** türü (Visual Studio 2017 yalnızca) eksik, seçin **açık Visual Studio yükleyicisi** sol bölmesinde **yeni proje** iletişim kutusu. Yükle seçeneği altında bulunan **C++ ile masaüstü geliştirme** içinde **isteğe bağlı** adlı bileşenleri bölümünde **C + +/ CLI desteği**.<br/>

1. Bir proje adı yazın.

   Varsayılan olarak, projeyi içeren çözüm yeni proje ile aynı ada sahiptir ancak farklı bir ad girebilirsiniz. İsterseniz, proje için farklı bir konum girebilirsiniz.

   Tıklayın **Tamam** yeni projeyi oluşturmak için.

1. Varsa **Çözüm Gezgini** görünmeyen, tıklayın **Çözüm Gezgini** üzerinde **görünümü** menüsü.

1. Yeni bir kaynak dosyası projeye ekleyin:

   - Sağ **kaynak dosyaları** klasöründe **Çözüm Gezgini**, işaret **Ekle**, tıklatıp **yeni öğe**.

   - Tıklayın **C++ dosyası (.cpp)** ve bir dosya adı yazın ve ardından **Ekle**.

   **.Cpp** dosya görünür **kaynak dosyaları** klasöründe **Çözüm Gezgini** ve kod girebileceğiniz bir sekmeli pencere görünür, bu dosyada istediğiniz.

1. Visual Studio'da yeni oluşturulan sekmesine tıklayın ve geçerli bir Visual C++ programı yazın veya kopyalayın ve örnek programlardan birini yapıştırın.

   Örneğin kullanabilirsiniz [nasıl yapılır: metin dosyaları yazma (C + +/ CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) örnek program (içinde **dosya işleme ve g/ç** düğümünün Programlama Kılavuzu).

   Örnek programı kullanırsanız, kullandığına dikkat edin `gcnew` anahtar sözcüğü yerine `new` bir .NET nesnesini ve oluştururken `gcnew` bir tanıtıcı döndürür (`^`) yerine bir işaretçi (`*`):

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   Yeni Visual C++ sözdizimi hakkında daha fazla bilgi için bkz. [çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md).

1. Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   **Çıkış** pencere konumunu yapı günlüğüne ve yapı durumunu belirten bir ileti gibi derleme ilerlemesi hakkında bilgileri görüntüler.

   Değişiklik yapmak ve bir yapı yapmadan programı çalıştırırsanız, bir iletişim kutusu projenin güncel olduğunu gösterebilir. Tıklamadan önce bu iletişim kutusundaki onay kutusunu işaretleyin **Tamam** dosyaları güncel sürümleri yerine her zaman sormadan kullanılması her zaman Visual Studio istiyorsanız, uygulama oluşturur.

1. Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

1. Programı çalıştırdığınızda örnek programı kullandıysanız bir metin dosyasının oluşturulduğunu belirten bir komut penceresi görüntülenir.

   **Textfile.txt** metin dosyası artık proje dizininde bulunur. Not Defteri'ni kullanarak bu dosyayı açabilirsiniz.

   > [!NOTE]
   > Boş CLR seçerek proje şablonu otomatik olarak `/clr` derleyici seçeneği. Bunu doğrulamak için projeye sağ **Çözüm Gezgini** tıklayıp **özellikleri**, iade edin **ortak dil çalışma zamanı desteği** seçeneği **Genel** düğümünün **yapılandırma özellikleri**.

## <a name="whats-next"></a>Yenilikler

**Önceki:** [izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
**Sonraki:** [izlenecek yol: komut satırında C programı derleme](../build/walkthrough-compile-a-c-program-on-the-command-line.md)<br/>

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>

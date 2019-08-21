---
title: 'İzlenecek yol: Aracı tabanlı uygulama oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 4a2fabd9ab4f358d40b17e662fb64ab70d01c58e
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631658"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>İzlenecek yol: Aracı tabanlı uygulama oluşturma

Bu konu, temel bir aracı tabanlı uygulamanın nasıl oluşturulacağını açıklamaktadır. Bu kılavuzda, bir metin dosyasından verileri zaman uyumsuz olarak okuyan bir aracı oluşturabilirsiniz. Uygulama, bu dosyanın içeriğinin sağlama toplamını hesaplamak için Adler-32 sağlama algoritmasını kullanır.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki konuları anlamanız gerekir:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a>Başlıklı

Bu izlenecek yol, aşağıdaki görevlerin nasıl gerçekleştirileceğini göstermektedir:

- [Konsol uygulaması oluşturma](#createapplication)

- [File_reader sınıfı oluşturma](#createagentclass)

- [Uygulamada file_reader sınıfını kullanma](#useagentclass)

##  <a name="createapplication"></a>Konsol uygulaması oluşturma

Bu bölümde, programın kullanacağı üstbilgi dosyalarına C++ başvuran bir konsol uygulamasının nasıl oluşturulacağı gösterilmektedir. İlk adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Bu sayfanın sol üst kısmında sürüm seçicinin doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Visual Studio 2019 C++ ' de bir konsol uygulaması oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden **Dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın. 

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, projenin adı olarak `BasicAgent` girin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

1. **Çözüm Gezgini**' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. **Yapılandırma özellikleri** > altında**C/C++** önceden derlenmişüstbilgiler > ön derlenmiş üstbilgisi oluştur ' ı seçin. > 

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Visual Studio 2017 C++ ve önceki sürümlerde bir konsol uygulaması oluşturmak için

1. **Dosya** menüsünde **Yeni**' ye ve ardından **Proje** ' ye tıklayarak **Yeni proje** iletişim kutusunu görüntüleyin.

1. **Yeni proje** iletişim kutusunda, **Proje türleri** bölmesinde  **C++ görsel** düğümünü seçin ve ardından **Şablonlar** bölmesinde **Win32 konsol uygulaması** ' nı seçin. Proje için bir ad yazın, örneğin `BasicAgent`, ve ardından **Win32 konsol uygulaması sihirbazını**göstermek için **Tamam** ' a tıklayın.

1. **Win32 konsol uygulaması Sihirbazı** Iletişim kutusunda **son**' a tıklayın.

::: moniker-end

1. *Pch. h* Içinde (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ), aşağıdaki kodu ekleyin:

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Agents. h üstbilgi dosyası, [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) sınıfının işlevlerini içerir.

1. Uygulamanın oluşturup çalıştırarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı derlemek için, **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulama başarıyla yapılandığında **hata ayıklama** menüsünde **hata ayıklamayı Başlat** ' a tıklayarak uygulamayı çalıştırın.

[[Üst](#top)]

##  <a name="createagentclass"></a>File_reader sınıfı oluşturma

Bu bölümde `file_reader` sınıfının nasıl oluşturulacağı gösterilmektedir. Çalışma zamanı, her aracıyı kendi bağlamında iş gerçekleştirecek şekilde zamanlar. Bu nedenle, işi zaman uyumlu olarak gerçekleştiren, ancak diğer bileşenleriyle zaman uyumsuz olarak etkileşim kuran bir aracı oluşturabilirsiniz. Sınıfı `file_reader` , belirli bir giriş dosyasından verileri okur ve bu dosyadaki verileri belirli bir hedef bileşene gönderir.

#### <a name="to-create-the-file_reader-class"></a>File_reader sınıfını oluşturmak için

1. Projenize yeni C++ bir üst bilgi dosyası ekleyin. Bunu yapmak için **Çözüm Gezgini**' deki **üstbilgi dosyaları** düğümüne sağ tıklayın, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın. **Şablonlar** bölmesinde **üst bilgi dosyası (. h)** öğesini seçin. **Yeni öğe Ekle** iletişim kutusunda, **ad** kutusuna yazın `file_reader.h` ve ardından **Ekle**' ye tıklayın.

1. File_reader. h içinde aşağıdaki kodu ekleyin.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. File_reader. h içinde, öğesinden `file_reader` `agent`türetilen adlı bir sınıf oluşturun.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Aşağıdaki veri üyelerini `private` sınıfınızın bölümüne ekleyin.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` Üye, aracının okuduğu dosya adıdır. Üye, aracının dosyanın içeriğini yazdığı bir [concurrency:: itarget nesnesidir.](../../parallel/concrt/reference/itarget-class.md) `_target` `_error` Üye, aracının ömrü boyunca oluşan tüm hataları barındırır.

1. `file_reader` Oluşturucularının sınıfının`file_reader` bölümüne aşağıdaki kodu ekleyin. `public`

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Her bir Oluşturucu aşırı yüklemesi `file_reader` , veri üyelerini ayarlar. İkinci ve üçüncü Oluşturucu aşırı yüklemesi, uygulamanızın aracısıyla belirli bir Zamanlayıcı kullanmasını sağlar. İlk aşırı yükleme, aracılarınız ile varsayılan zamanlayıcıyı kullanır.

1. `get_error` Yöntemini `file_reader` sınıfının genel bölümüne ekleyin.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` Yöntemi, aracının ömrü boyunca oluşan tüm hataları alır.

1. Sınıfınızın `protected` bölümünde [concurrency:: Agent:: Run](reference/agent-class.md#run) yöntemini uygulayın.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` Yöntemi dosyayı açar ve verileri okur. Yöntemi `run` , dosya işleme sırasında oluşan hataları yakalamak için özel durum işlemeyi kullanır.

   Bu yöntemin dosyadaki verileri okuduğu her seferinde, bu verileri hedef arabelleğe göndermek için [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevini çağırır. İşlemin sonunu belirtmek için boş dizeyi hedef arabelleğine gönderir.

Aşağıdaki örnek, File_reader. h öğesinin tüm içeriğini gösterir.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[Üst](#top)]

##  <a name="useagentclass"></a>Uygulamada file_reader sınıfını kullanma

Bu bölümde, `file_reader` bir metin dosyasının içeriğini okumak için sınıfının nasıl kullanılacağı gösterilmektedir. Ayrıca, bu dosya verilerini alan ve Adler-32 sağlama toplamını hesaplayan bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesinin nasıl oluşturulacağını gösterir.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>File_reader sınıfını Uygulamanızda kullanmak için

1. BasicAgent. cpp içinde aşağıdaki `#include` ifadeyi ekleyin.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent. cpp içinde aşağıdaki `using` yönergeleri ekleyin.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. İşlevinde, işleme sonuna işaret eden bir [eşzamanlılık:: Event](../../parallel/concrt/reference/event-class.md) nesnesi oluşturun. `_tmain`

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Veri aldığında `call` sağlama toplamını güncelleştiren bir nesne oluşturun.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Bu `call` nesne, işleme sonuna `event` işaret etmek üzere boş dizeyi aldığında nesneyi de ayarlar.

1. Test. `file_reader` txt dosyasından okuyan bir nesne oluşturun ve bu dosyanın `call` içeriğini nesnesine yazar.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Aracıyı başlatın ve bitmesini bekleyin.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. `call` Nesnenin tüm verileri almasını ve tamamlamasını bekleyin.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. Hatalar için dosya okuyucuyu denetleyin. Bir hata oluşmazsa, son Adler-32 toplamını hesaplayın ve toplamı konsola yazdırın.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

Aşağıdaki örnekte, tüm BasicAgent. cpp dosyası gösterilmektedir.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[Üst](#top)]

## <a name="sample-input"></a>Örnek Giriş

Bu, metin. txt giriş dosyasının örnek içeriğidir:

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>Örnek Çıktı

Örnek girişle birlikte kullanıldığında, bu program aşağıdaki çıktıyı üretir:

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>Güçlü Programlama

Veri üyelerine eşzamanlı erişimi engellemek için, sınıfınızın `protected` veya `private` bölümüne iş yapan Yöntemler eklemenizi öneririz. Yalnızca, aracıınızın `public` bölümüne veya aracıdan ileti gönderen ya da alan yöntemler ekleyin.

Aracınızı tamamlandı durumuna taşımak için her zaman [concurrency:: Agent::d bir](reference/agent-class.md#done) yöntemi çağırın. Genellikle bu yöntemi `run` yönteminden döndürmeden önce çağırın.

## <a name="next-steps"></a>Sonraki Adımlar

Aracı tabanlı bir uygulamanın başka bir örneği için bkz [. İzlenecek yol: Kilitlenmeyi](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)engellemek için JOIN 'i kullanma.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

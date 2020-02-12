---
title: 'İzlenecek Yol: Aracı Temelli Uygulama Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 3ece04811a75fba22db447875dc6ed08c22987b5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142049"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>İzlenecek Yol: Aracı Temelli Uygulama Oluşturma

Bu konu, temel bir aracı tabanlı uygulamanın nasıl oluşturulacağını açıklamaktadır. Bu kılavuzda, bir metin dosyasından verileri zaman uyumsuz olarak okuyan bir aracı oluşturabilirsiniz. Uygulama, bu dosyanın içeriğinin sağlama toplamını hesaplamak için Adler-32 sağlama algoritmasını kullanır.

## <a name="prerequisites"></a>Prerequisites

Bu izlenecek yolu tamamlamak için aşağıdaki konuları anlamanız gerekir:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

## <a name="top"></a>Başlıklı

Bu izlenecek yol, aşağıdaki görevlerin nasıl gerçekleştirileceğini göstermektedir:

- [Konsol uygulaması oluşturma](#createapplication)

- [File_reader sınıfı oluşturma](#createagentclass)

- [Uygulamada file_reader sınıfını kullanma](#useagentclass)

## <a name="createapplication"></a>Konsol uygulaması oluşturma

Bu bölümde, programın kullanacağı üstbilgi dosyalarına C++ başvuran bir konsol uygulamasının nasıl oluşturulacağı gösterilmektedir. İlk adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Bu sayfanın sol üst kısmında sürüm seçicinin doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Visual Studio 2019 C++ ' de bir konsol uygulaması oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden **dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın. 

1. Filtre uygulanmış proje türleri listesinden **konsol uygulaması** ' nı seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, projenin adı olarak `BasicAgent` girin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

1. **Çözüm Gezgini**' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. **Yapılandırma özellikleri** ' nin altında > önceden derlenmiş üst **bilgi** > ön derlenmiş **üstbilgiler** **Oluştur**' > **aC++**  tıklayın.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Visual Studio 2017 C++ ve önceki sürümlerde bir konsol uygulaması oluşturmak için

1. **Dosya** menüsünde **Yeni**' ye ve ardından **Proje** ' ye tıklayarak **Yeni proje** iletişim kutusunu görüntüleyin.

1. **Yeni proje** iletişim kutusunda, **Proje türleri** bölmesinde  **C++ görsel** düğümünü seçin ve ardından **Şablonlar** bölmesinde **Win32 konsol uygulaması** ' nı seçin. Proje için bir ad yazın, örneğin, `BasicAgent`ve ardından **Tamam** ' a tıklayarak **Win32 konsol uygulaması Sihirbazı 'nı**görüntüleyin.

1. **Win32 konsol uygulaması Sihirbazı** Iletişim kutusunda **son**' a tıklayın.

::: moniker-end

1. *Pch. h* Içinde (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ), aşağıdaki kodu ekleyin:

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Agents. h üstbilgi dosyası, [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) sınıfının işlevlerini içerir.

1. Uygulamanın oluşturup çalıştırarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı derlemek için, **Yapı** menüsünde **çözüm oluştur**' a tıklayın. Uygulama başarıyla yapılandığında **hata ayıklama** menüsünde **hata ayıklamayı Başlat** ' a tıklayarak uygulamayı çalıştırın.

[[Üst](#top)]

## <a name="createagentclass"></a>File_reader sınıfı oluşturma

Bu bölümde `file_reader` sınıfının nasıl oluşturulacağı gösterilmektedir. Çalışma zamanı, her aracıyı kendi bağlamında iş gerçekleştirecek şekilde zamanlar. Bu nedenle, işi zaman uyumlu olarak gerçekleştiren, ancak diğer bileşenleriyle zaman uyumsuz olarak etkileşim kuran bir aracı oluşturabilirsiniz. `file_reader` sınıfı, belirli bir giriş dosyasından verileri okur ve bu dosyadaki verileri belirli bir hedef bileşene gönderir.

#### <a name="to-create-the-file_reader-class"></a>File_reader sınıfını oluşturmak için

1. Projenize yeni C++ bir üst bilgi dosyası ekleyin. Bunu yapmak için **Çözüm Gezgini**' deki **üstbilgi dosyaları** düğümüne sağ tıklayın, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın. **Şablonlar** bölmesinde **üst bilgi dosyası (. h)** öğesini seçin. **Yeni öğe Ekle** iletişim kutusunda, **ad** kutusuna `file_reader.h` yazın ve ardından **Ekle**' ye tıklayın.

1. File_reader. h 'de aşağıdaki kodu ekleyin.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. File_reader. h 'de, `agent`türetilen `file_reader` adında bir sınıf oluşturun.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Aşağıdaki veri üyelerini sınıfınızın `private` bölümüne ekleyin.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` üyesi, aracının okuduğu dosya adıdır. `_target` üyesi, aracının dosyanın içeriğini yazdığı bir [concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) nesnesidir. `_error` üyesi, aracının ömrü boyunca oluşan tüm hataları barındırır.

1. `file_reader` oluşturucuları için aşağıdaki kodu `file_reader` sınıfının `public` bölümüne ekleyin.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Her bir Oluşturucu aşırı yüklemesi `file_reader` veri üyelerini ayarlar. İkinci ve üçüncü Oluşturucu aşırı yüklemesi, uygulamanızın aracısıyla belirli bir Zamanlayıcı kullanmasını sağlar. İlk aşırı yükleme, aracılarınız ile varsayılan zamanlayıcıyı kullanır.

1. `get_error` yöntemini `file_reader` sınıfının public bölümüne ekleyin.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` yöntemi, aracının ömrü boyunca oluşan tüm hataları alır.

1. Sınıfınızın `protected` bölümünde [concurrency:: Agent:: Run](reference/agent-class.md#run) yöntemini uygulayın.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` yöntemi dosyayı açar ve verileri okur. `run` yöntemi dosya işleme sırasında oluşan hataları yakalamak için özel durum işlemeyi kullanır.

   Bu yöntemin dosyadaki verileri okuduğu her seferinde, bu verileri hedef arabelleğe göndermek için [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevini çağırır. İşlemin sonunu belirtmek için boş dizeyi hedef arabelleğine gönderir.

Aşağıdaki örnek file_reader. h öğesinin tüm içeriğini gösterir.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[Üst](#top)]

## <a name="useagentclass"></a>Uygulamada file_reader sınıfını kullanma

Bu bölümde, bir metin dosyasının içeriğini okumak için `file_reader` sınıfının nasıl kullanılacağı gösterilmektedir. Ayrıca, bu dosya verilerini alan ve Adler-32 sağlama toplamını hesaplayan bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesinin nasıl oluşturulacağını gösterir.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>File_reader sınıfını Uygulamanızda kullanmak için

1. BasicAgent. cpp içinde aşağıdaki `#include` ifadesini ekleyin.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent. cpp içinde aşağıdaki `using` yönergelerini ekleyin.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. `_tmain` işlevinde, işleme sonuna işaret eden bir [eşzamanlılık:: Event](../../parallel/concrt/reference/event-class.md) nesnesi oluşturun.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Veri alırken sağlama toplamını güncelleştiren bir `call` nesnesi oluşturun.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Bu `call` nesnesi, işleme sonuna işaret etmek üzere boş dizeyi aldığında `event` nesnesini de ayarlar.

1. Test. txt dosyasından okuyan `file_reader` nesnesi oluşturun ve bu dosyanın içeriğini `call` nesnesine yazar.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Aracıyı başlatın ve bitmesini bekleyin.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. `call` nesnesinin tüm verileri almasını ve tamamlamasını bekleyin.

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

Veri üyelerine eşzamanlı erişimin engellenmesi için, sınıfınızın `protected` veya `private` bölümüne iş gerçekleştiren Yöntemler eklemenizi öneririz. Yalnızca sınıfınızın `public` bölümüne veya aracıdan ileti gönderen veya alan yöntemler ekleyin.

Aracınızı tamamlandı durumuna taşımak için her zaman [concurrency:: Agent::d bir](reference/agent-class.md#done) yöntemi çağırın. Bu yöntemi genellikle `run` yönteminden döndürmeden önce çağırın.

## <a name="next-steps"></a>Sonraki Adımlar

Aracı tabanlı bir uygulamanın başka bir örneği için bkz. [Izlenecek yol: birleştirmeyi engellemek için birleştirmeyi kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[İzlenecek Yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

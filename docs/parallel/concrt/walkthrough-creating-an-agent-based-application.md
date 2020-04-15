---
title: 'İzlenecek Yol: Aracı Temelli Uygulama Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 20197786e3d3c2d34d29af748c1cc073902cf70d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377453"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>İzlenecek Yol: Aracı Temelli Uygulama Oluşturma

Bu konu, temel aracı tabanlı bir uygulamanın nasıl oluşturulacağını açıklar. Bu izne, metin dosyasındaki verileri eşit bir şekilde okuyan bir aracı oluşturabilirsiniz. Uygulama, bu dosyanın içeriğinin denetimini hesaplamak için Adler-32 checksum algoritmasını kullanır.

## <a name="prerequisites"></a>Ön koşullar

Bu gözden geçirmeyi tamamlamak için aşağıdaki konuları anlamanız gerekir:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a>Bölüm

Bu izlik, aşağıdaki görevlerin nasıl gerçekleştirildirilebildiğini gösterir:

- [Konsol Uygulaması Oluşturma](#createapplication)

- [file_reader Sınıfı Oluşturma](#createagentclass)

- [Uygulamada file_reader Sınıfını Kullanma](#useagentclass)

## <a name="creating-the-console-application"></a><a name="createapplication"></a>Konsol Uygulamasını Oluşturma

Bu bölümde, programın kullanacağı üstbilgi dosyalarına başvurulan bir C++ konsol uygulamasının nasıl oluşturulacağı gösterilmektedir. İlk adımlar Visual Studio'nun hangi sürümünü kullandığınıza bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Visual Studio 2019'da C++ konsol uygulaması oluşturmak için

1. Ana menüden, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **Konsol'a**ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Konsol Uygulaması'nı** seçin ve **ardından İleri'yi**seçin. Sonraki sayfada, projenin `BasicAgent` adı olarak girin ve istenirse proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

1. **Çözüm Gezgini'ndeki**proje düğümüne sağ tıklayın ve **Özellikler'i**seçin. **Yapılandırma Özellikleri** > **Altında C/C++** > **Önceden Derlenmiş Üstbilgi** > **Önceden Derlenmiş üstbilgi** **oluştur'u**seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Visual Studio 2017 ve önceki yıllarda C++ konsol uygulaması oluşturmak için

1. **Dosya** menüsünde **Yeni'yi**tıklatın ve ardından **Yeni Proje** iletişim kutusunu görüntülemek için **Project'i** tıklatın.

1. Yeni **Proje** iletişim kutusunda, **Proje türleri** bölmesinde **Visual C++** düğümünü seçin ve ardından **Şablonlar** bölmesinde **Win32 Konsol Uygulaması'nı** seçin. Örneğin `BasicAgent`proje için bir ad yazın ve **Win32 Konsol Uygulama Sihirbazı'nı**görüntülemek için **Tamam'ı** tıklatın.

1. **Win32 Konsol Uygulama Sihirbazı** iletişim kutusunda **Finish'i**tıklatın.

::: moniker-end

1. *Pch.h* (Visual Studio 2017 ve önceki*stdafx.h)* olarak aşağıdaki kodu ekleyin:

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Üstbilgi dosyası aracıları.h eşzamanlılık işlevselliğini [içerir::aracı](../../parallel/concrt/reference/agent-class.md) sınıfı.

1. Uygulamanın oluşturularak ve çalıştırılarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı oluşturmak için **Yapı** menüsünde **Çözüm Oluştur'u**tıklatın. Uygulama başarılı bir şekilde yapılsa, **Hata Ayıklama** Başlat menüsünde **Hata Ayıklama başlat'ı** tıklatarak uygulamayı çalıştırın.

[[Üst](#top)]

## <a name="creating-the-file_reader-class"></a><a name="createagentclass"></a>file_reader Sınıfı Oluşturma

Bu bölümde `file_reader` sınıf nasıl oluşturulacak gösterilmektedir. Çalışma zamanı, her aracının çalışmayı kendi bağlamında gerçekleştirmesini zamanlar. Bu nedenle, işi eşzamanlı olarak gerçekleştiren, ancak diğer bileşenlerle eşzamanlı olarak etkileşimde bulunan bir aracı oluşturabilirsiniz. Sınıf, `file_reader` belirli bir giriş dosyasındaki verileri okur ve bu dosyadaki verileri belirli bir hedef bileşene gönderir.

#### <a name="to-create-the-file_reader-class"></a>File_reader sınıfını oluşturmak için

1. Projenize yeni bir C++ üstbilgi dosyası ekleyin. Bunu yapmak için, **Çözüm Gezgini'ndeki** **Üstbilgi Dosyaları** düğümüne sağ tıklayın, **Ekle'yi**tıklatın ve ardından **Yeni Öğe'yi**tıklatın. **Şablonlar** bölmesinde **Üstbilgi Dosyası (.h)** seçeneğini belirleyin. Yeni **Öğe Ekle** iletişim kutusunda `file_reader.h` Ad **kutusuna** yazın ve sonra **Ekle'yi**tıklatın.

1. file_reader.h olarak, aşağıdaki kodu ekleyin.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. file_reader.h'de, `file_reader` `agent`'den türeyen bir sınıf oluşturun.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Aşağıdaki veri üyelerini sınıfınızın bölümüne `private` ekleyin.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   Üye, `_file_name` aracının okuduğu dosya adıdır. `_target` Üye bir [eşzamanlılık::ITarget](../../parallel/concrt/reference/itarget-class.md) nesnesi aracısı dosyanın içeriğini yazar. Üye, `_error` aracının ömrü boyunca meydana gelen herhangi bir hatayı tutar.

1. Sınıfın `file_reader` `public` bölümüne oluşturucular için aşağıdaki kodu ekleyin. `file_reader`

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Her yapıcı veya aşırı `file_reader` yük veri üyelerini ayarlar. İkinci ve üçüncü yapıcı aşırı yükleme, uygulamanızın aracınızla belirli bir zamanlayıcı kullanmasını sağlar. İlk aşırı yükleme aracınızla birlikte varsayılan zamanlayıcıyı kullanır.

1. `get_error` Yöntemi `file_reader` sınıfın ortak bölümüne ekleyin.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   Yöntem, `get_error` aracının ömrü boyunca oluşan herhangi bir hatayı alır.

1. [Eşzamanlılık uygulayın::agent::sınıfının](reference/agent-class.md#run) `protected` bölümünde çalıştır yöntemi.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

Yöntem `run` dosyayı açar ve dosyadaki verileri okur. Yöntem, `run` dosya işleme sırasında oluşan hataları yakalamak için özel durum işleme kullanır.

   Bu yöntem dosyadaki verileri her okuduğunda, [eşzamanlılığı çağırır::bu](reference/concurrency-namespace-functions.md#asend) verileri hedef arabelleğe göndermek için asend işlevi. İşlemin sonunu belirtmek için boş dizeyi hedef arabellesine gönderir.

Aşağıdaki örnek, file_reader.h.'nin tüm içeriğini gösterir.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[Üst](#top)]

## <a name="using-the-file_reader-class-in-the-application"></a><a name="useagentclass"></a>Uygulamada file_reader Sınıfını Kullanma

Bu bölümde, bir `file_reader` metin dosyasının içeriğini okumak için sınıfın nasıl kullanılacağı gösterilmektedir. Ayrıca eşzamanlılık nasıl oluşturulacak [gösterir::bu](../../parallel/concrt/reference/call-class.md) dosya verilerini alan ve Adler-32 checksum hesaplar çağrı nesnesi.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>File_reader sınıfını Uygulamanızda kullanmak için

1. BasicAgent.cpp'de aşağıdaki `#include` ifadeyi ekleyin.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent.cpp'de aşağıdaki `using` yönergeleri ekleyin.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. İşlevde, `_tmain` işlemin sonunu işaret eden bir [eşzamanlılık::olay](../../parallel/concrt/reference/event-class.md) nesnesi oluşturun.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Veri `call` aldığında checksum güncelleyen bir nesne oluşturun.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Bu `call` nesne, `event` işlemenin sonunu işaret etmek için boş dize aldığında da nesneyi ayarlar.

1. Test.txt dosyasından okuyan ve dosyanın içeriğini `file_reader` `call` nesneye yazan bir nesne oluşturun.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Aracıyı başlatın ve bitmesini bekleyin.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. Nesnenin `call` tüm verileri almasını ve bitirmesini bekleyin.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. Hataolup etmeyin dosya okuyucuyu denetleyin. Hata oluştuysa, son Adler-32 toplamını hesaplayın ve toplamı konsola yazdırın.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

Aşağıdaki örnek, BasicAgent.cpp dosyasının tamamını gösterir.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[Üst](#top)]

## <a name="sample-input"></a>Örnek Giriş

Bu giriş dosyası text.txt örnek içeriği:

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>Örnek Çıktı

Örnek girişi ile kullanıldığında, bu program aşağıdaki çıktıyı üretir:

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>Güçlü Programlama

Veri üyelerine eşzamanlı erişimi önlemek için, çalışma gerçekleştiren yöntemleri `protected` sınıfınızın bölümüne eklemenizi `private` öneririz. Yalnızca aracıya veya aracıdan sınıfınızın `public` bölümüne ileti gönderen veya alan yöntemler ekleyin.

Aracınızı her zaman [eşzamanlılık çağırın:::daracınızı](reference/agent-class.md#done) tamamlanan duruma taşımak için tek bir yöntem. Yöntemden `run` dönmeden önce genellikle bu yöntemi çağırırsınız.

## <a name="next-steps"></a>Sonraki Adımlar

Aracı tabanlı bir uygulamanın başka bir örneği için [bkz.](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[İzlenecek Yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

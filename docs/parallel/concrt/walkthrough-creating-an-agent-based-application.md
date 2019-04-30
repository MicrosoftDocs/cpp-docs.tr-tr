---
title: 'İzlenecek yol: Aracı tabanlı uygulama oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 1d55c9879a3dd90bb4a40b61a3bf958dbe960bc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378069"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>İzlenecek yol: Aracı tabanlı uygulama oluşturma

Bu konu, temel bir aracı tabanlı uygulamanın nasıl oluşturulacağını açıklar. Bu kılavuzda, bir metin dosyasından verileri okur, zaman uyumsuz olarak bir aracı oluşturabilirsiniz. Uygulama, bu dosyanın içeriğini toplamını hesaplamak için Adler 32 sağlama algoritması kullanır.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki konuları anlamanız gerekir:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> Bölümleri

Bu izlenecek yol aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:

- [Konsol uygulaması oluşturma](#createapplication)

- [File_reader sınıfı oluşturma](#createagentclass)

- [File_reader sınıfını uygulamada kullanma](#useagentclass)

##  <a name="createapplication"></a> Konsol uygulaması oluşturma

Bu bölümde, programın kullanacağı üstbilgi dosyalarına başvuran bir Visual C++ konsol uygulaması oluşturma işlemi gösterilmektedir.

#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>Win32 Konsol Uygulama Sihirbazı'nı kullanarak bir Visual C++ uygulaması oluşturmak için

1. Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje** görüntülenecek **yeni proje** iletişim kutusu.

1. İçinde **yeni proje** iletişim kutusunda **Visual C++** düğümünde **proje türleri** bölmesi ve ardından **Win32 konsol uygulaması** içinde **şablonları** bölmesi. Proje için bir ad yazın örneğin, `BasicAgent`ve ardından **Tamam** görüntülenecek **Win32 Konsol Uygulama Sihirbazı**.

1. İçinde **Win32 Konsol Uygulama Sihirbazı** iletişim kutusu, tıklayın **son**.

1. Stdafx.h öğesinde aşağıdaki kodu ekleyin.

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Üst bilgi dosyası agents.h işlevlerini içeren [concurrency::agent](../../parallel/concrt/reference/agent-class.md) sınıfı.

1. Oluşturma ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Uygulama derlemek için **derleme** menüsünde tıklatın **Çözümü Derle**. Uygulama başarıyla derlenirse tıklayarak uygulamayı çalıştırmak **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.

[[Üst](#top)]

##  <a name="createagentclass"></a> File_reader sınıfı oluşturma

Bu bölüm nasıl oluşturulacağını gösterir `file_reader` sınıfı. Çalışma zamanı kendi bağlam içinde iş gerçekleştirmek için her bir aracı zamanlar. Bu nedenle, iş zaman uyumlu olarak yapar, ancak zaman uyumsuz olarak diğer bileşenlerle etkileşimi bir aracı oluşturabilirsiniz. `file_reader` Sınıfı belirli bir giriş dosyadan verileri okur ve belirtilen hedef bileşen bu dosyadan verileri gönderir.

#### <a name="to-create-the-filereader-class"></a>File_reader sınıfını oluşturmak için

1. Yeni bir C++ üstbilgi dosyası projenize ekleyin. Bunu yapmak için sağ **üst bilgi dosyaları** düğümünde **Çözüm Gezgini**, tıklayın **Ekle**ve ardından **yeni öğe**. İçinde **şablonları** bölmesinde **üst bilgi dosyası (.h)**. İçinde **Yeni Öğe Ekle** iletişim kutusuna `file_reader.h` içinde **adı** kutusuna ve ardından **Ekle**.

1. File_reader.h içinde aşağıdaki kodu ekleyin.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. File_reader.h içinde adlı bir sınıf oluşturmanız `file_reader` türetilen `agent`.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Aşağıdaki veri üyelerini ekleyin `private` sınıfınızın bölümü.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` Üyesi olan aracı okur dosya adı. `_target` Üyesi olan bir [CONCURRENCY::ıtarget](../../parallel/concrt/reference/itarget-class.md) nesne aracı içeriğini bir dosyaya yazar. `_error` Üye Aracısı'nın ömrü sırasında oluşan hataları içerir.

1. İçin aşağıdaki kodu ekleyin `file_reader` oluşturucular `public` bölümünü `file_reader` sınıfı.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Her oluşturucu aşırı yüklemesi ayarlar `file_reader` veri üyeleri. İkinci ve üçüncü kurucu aşırı yükleme, belirli bir Zamanlayıcı, aracı ile kullanmak için uygulamanızı sağlar. İlk aşırı yükleme varsayılan Zamanlayıcı, aracı ile kullanır.

1. Ekleme `get_error` yöntemi genel bölümüne `file_reader` sınıfı.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` Yöntemi Aracısı'nın ömrü sırasında oluşan hataları alır.

1. Uygulama [concurrency::agent::run](reference/agent-class.md#run) yönteminde `protected` sınıfınızın bölümü.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` Yöntemi dosya açılır ve buradan verileri okur. `run` Yöntemi dosya işlem sırasında oluşan hataları yakalamak için özel durum işleme kullanır.

   Bu yöntem, dosyadan verileri okur her seferinde onu çağıran [concurrency::asend](reference/concurrency-namespace-functions.md#asend) hedef arabelleğe verileri göndermek için işlevi. Bu işleme sonunu belirtmek için hedef arabelleği boş bir dize gönderir.

Aşağıdaki örnek file_reader.h tam içeriğini gösterir.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[Üst](#top)]

##  <a name="useagentclass"></a> File_reader sınıfını uygulamada kullanma

Bu bölümde, nasıl kullanılacağını gösterir `file_reader` bir metin dosyasının içeriğini okumak için sınıf. Ayrıca nasıl oluşturulacağını gösterir bir [concurrency::call](../../parallel/concrt/reference/call-class.md) nesnesini bu dosya verilerini alır ve Adler 32 toplamını hesaplar.

#### <a name="to-use-the-filereader-class-in-your-application"></a>File_reader sınıfını Uygulamanızda kullanmak için

1. BasicAgent.cpp içinde aşağıdaki ekleme `#include` deyimi.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent.cpp içinde aşağıdaki ekleme `using` yönergeleri.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. İçinde `_tmain` işlev, oluşturun bir [concurrency::event](../../parallel/concrt/reference/event-class.md) işleme sonuna sinyalleri nesne.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Oluşturma bir `call` veri aldığında sağlama toplamı güncelleştirmeleri nesnesi.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Bu `call` nesnesi de ayarlar `event` nesnesi boş bir dize işleme sonuna belirten aldığında.

1. Oluşturma bir `file_reader` dosya test.txt okur ve içeriğini bu dosyaya yazan nesne `call` nesne.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Aracısı'nı başlatın ve bitmesini bekleyin.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. Bekle `call` tüm veri almak ve tamamlamak için nesne.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. Dosya okuyucu hataları denetleyin. Herhangi bir hata oluştuysa, son Adler 32 toplamı hesaplamak ve toplamı konsola yazdırma.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

Aşağıdaki örnek, tam BasicAgent.cpp dosya gösterir.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[Üst](#top)]

## <a name="sample-input"></a>Örnek Giriş

Bu giriş dosyası text.txt örnek içeriği.

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>Örnek Çıktı

Örnek giriş ile kullanıldığında, bu program şu çıktıyı üretir:

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>Güçlü Programlama

Veri üyeleri için eş zamanlı erişimi engellemek için işi gerçekleştiren yöntemler eklemenizi öneririz `protected` veya `private` sınıfınızın bölümü. Yalnızca gelen aracıya veya ileti gönderip yöntemleri ekleyin `public` sınıfınızın bölümü.

Her zaman çağrı [concurrency::agent:: Bitti](reference/agent-class.md#done) aracınızı tamamlanmış duruma taşımak için yöntemi. Genellikle gelen dönmeden önce bu yöntemi çağırmanız `run` yöntemi.

## <a name="next-steps"></a>Sonraki Adımlar

Aracı tabanlı bir uygulamaya başka bir örnek için bkz [izlenecek yol: Kilitlenmeyi önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

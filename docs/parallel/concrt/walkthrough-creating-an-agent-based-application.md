---
title: 'İzlenecek yol: aracı temelli uygulama oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68c4b389bdd8f1121a59bce1a0ca8942f077e062
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377179"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>İzlenecek Yol: Aracı Temelli Uygulama Oluşturma

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

     The header file agents.h contains the functionality of the [concurrency::agent](../../parallel/concrt/reference/agent-class.md) class.

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

     The `_file_name` member is the file name that the agent reads from. The `_target` member is a [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) object that the agent writes the contents of the file to. The `_error` member holds any error that occurs during the life of the agent.

1. İçin aşağıdaki kodu ekleyin `file_reader` oluşturucular `public` bölümünü `file_reader` sınıfı.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

     Each constructor overload sets the `file_reader` data members. The second and third constructor overload enables your application to use a specific scheduler with your agent. The first overload uses the default scheduler with your agent.

1. Ekleme `get_error` yöntemi genel bölümüne `file_reader` sınıfı.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

     The `get_error` method retrieves any error that occurs during the life of the agent.

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

     This `call` object also sets the `event` object when it receives the empty string to signal the end of processing.

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

Aracı tabanlı bir uygulamaya başka bir örnek için bkz [izlenecek yol: kilitlenmeyi önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)<br/>
[İzlenecek Yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)


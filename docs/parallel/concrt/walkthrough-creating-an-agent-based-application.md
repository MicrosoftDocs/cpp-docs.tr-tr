---
title: "İzlenecek yol: aracı temelli uygulama oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a49c8deb9185b024dfcca977ab229bf594e05101
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-an-agent-based-application"></a>İzlenecek Yol: Aracı Temelli Uygulama Oluşturma
Bu konuda, temel bir aracı temelli uygulama oluşturma açıklanmaktadır. Bu kılavuzda, zaman uyumsuz olarak bir metin dosyasından veri okuyan bir aracı oluşturabilirsiniz. Uygulama, dosyanın içeriğini sağlama hesaplamak için Adler-32 sağlama toplamı algoritmayı kullanır.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki konuları anlamanız gerekir:  
  
- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)  
  
- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)  
  
- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a>Bölümler  
 Bu kılavuz aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:  
  
- [Konsol uygulaması oluşturma](#createapplication)  
  
- [File_reader sınıfı oluşturma](#createagentclass)  
  
- [Sınıf file_reader uygulamasında kullanma](#useagentclass)  
  
##  <a name="createapplication"></a>Konsol uygulaması oluşturma  
 Bu bölümde programın kullanacağı üstbilgi dosyaları başvuruda bulunan bir Visual C++ konsol uygulamasının nasıl oluşturulacağını gösterir.  
  
#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>Win32 Konsol Uygulama Sihirbazı'nı kullanarak bir Visual C++ uygulaması oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual C++** düğümünde **proje türleri** bölmesi ve ardından **Win32 konsol uygulaması** içinde **şablonları** bölmesi. Proje için bir ad yazın, örneğin, `BasicAgent`ve ardından **Tamam** görüntülemek için **Win32 Konsol Uygulama Sihirbazı'nı**.  
  
3.  İçinde **Win32 Konsol Uygulama Sihirbazı'nı** iletişim kutusu, tıklatın **son**.  
  
4.  Stdafx.h'de aşağıdaki kodu ekleyin.  
  
 [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]  
  
     Üstbilgi dosyası agents.h işlevselliğini içerir [concurrency::agent](../../parallel/concrt/reference/agent-class.md) sınıfı.  
  
5.  Derleme ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Uygulama üzerinde oluşturmak için **yapı** menüsünde tıklatın **yapı çözümü**. Uygulama başarıyla oluşturursa tıklayarak uygulamayı çalıştırın **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.  
  
 [[Üst](#top)]  
  
##  <a name="createagentclass"></a>File_reader sınıfı oluşturma  
 Bu bölümde nasıl oluşturulacağını gösterir `file_reader` sınıfı. Çalışma Zamanı İş kendi bağlamda gerçekleştirmek için her bir aracının zamanlar. Bu nedenle, iş zaman uyumlu olarak gerçekleştirir, ancak diğer bileşenlerle etkileşimi zaman uyumsuz olarak bir aracı oluşturabilirsiniz. `file_reader` Sınıfı belirli bir giriş dosyasından veri okur ve verileri bu dosyadan verilen hedef bileşenine gönderir.  
  
#### <a name="to-create-the-filereader-class"></a>File_reader sınıfını oluşturmak için  
  
1.  Yeni bir C++ üstbilgi dosyası projenize ekleyin. Bunu yapmak için sağ **üstbilgi dosyaları** düğümünde **Çözüm Gezgini**, tıklatın **Ekle**ve ardından **yeni öğe**. İçinde **şablonları** bölmesinde, **üstbilgi dosyası (.h)**. İçinde **Yeni Öğe Ekle** iletişim kutusuna `file_reader.h` içinde **adı** kutusuna ve ardından **Ekle**.  
  
2.  File_reader.h içinde aşağıdaki kodu ekleyin.  
  
 [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  File_reader.h içinde adlı bir sınıf oluşturun `file_reader` , türetilen `agent`.  
  
 [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  Aşağıdaki veri üye ekleme `private` sınıfınızın bölümü.  
  
 [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]  
  
     `_file_name` Üyesidir aracı okur dosya adı. `_target` Üye olduğu bir [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) aracı dosyasının içeriğini yazar nesne. `_error` Üye Aracısı'nın ömrü sırasında oluşan hataları tutar.  
  
5.  İçin aşağıdaki kodu ekleyip `file_reader` kurucusuna `public` bölümünü `file_reader` sınıfı.  
  
 [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]  
  
     Her Oluşturucusu aşırı ayarlar `file_reader` veri üyeleri. İkinci ve üçüncü Oluşturucusu aşırı belirli Zamanlayıcı aracınızı ile kullanmak için uygulamanızı sağlar. İlk aşırı aracınızı ile varsayılan Zamanlayıcısı'nı kullanır.  
  
6.  Ekleme `get_error` yöntemi ortak bölümüne `file_reader` sınıfı.  
  
 [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]  
  
     `get_error` Yöntemi Aracısı'nın ömrü sırasında oluşan hataları alır.  
  

7.  Uygulama [concurrency::agent::run](reference/agent-class.md#run) yönteminde `protected` sınıfınızın bölümü.  

  
 [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]  
  
`run` Yöntemi dosyayı açar ve ondan veri okur. `run` Yöntemi dosya işlem sırasında oluşan hataları yakalamak için özel durum işleme kullanır.  
  
   Bu yöntem dosyasından veri okuyan her zaman çağırır [concurrency::asend](reference/concurrency-namespace-functions.md#asend) bu verileri hedef arabelleği gönderme işlevi. Boş dize işleme sonunu göstermek için hedef arabelleğini gönderir.  

  
 Aşağıdaki örnek file_reader.h tam içeriğini gösterir.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]  
  
 [[Üst](#top)]  
  
##  <a name="useagentclass"></a>Sınıf file_reader uygulamasında kullanma  
 Bu bölümde nasıl kullanılacağını gösterir `file_reader` bir metin dosyasının içeriğini okumak için sınıf. Ayrıca nasıl oluşturulacağını gösterir bir [concurrency::call](../../parallel/concrt/reference/call-class.md) bu dosya verileri alır ve kendi Adler-32 sağlama toplamı hesaplar nesnesi.  
  
#### <a name="to-use-the-filereader-class-in-your-application"></a>File_reader sınıfını Uygulamanızda kullanmak için  
  
1.  BasicAgent.cpp içinde aşağıdaki ekleme `#include` deyimi.  
  
 [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  BasicAgent.cpp içinde aşağıdaki ekleme `using` yönergeleri.  
  
 [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  İçinde `_tmain` işlev, oluşturma bir [concurrency::event](../../parallel/concrt/reference/event-class.md) işleme sonuna sinyalleri nesnesi.  
  
 [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  Oluşturma bir `call` veri aldığında sağlama toplamı güncelleştirmeleri nesnesi.  
  
 [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     Bu `call` nesne ayrıca ayarlar `event` nesne boş dize işleme sonuna sinyal aldığında.  
  
5.  Oluşturma bir `file_reader` dosya sınama.txt okuyan ve bu dosyanın içeriğini yazar nesne `call` nesne.  
  
 [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  Aracısı'nı başlatın ve son tamamlanmasını bekleyin.  
  
 [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  Bekle `call` tüm verileri almak ve tamamlamak için nesne.  
  
 [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  Dosya okuyucu hataları denetleyin. Herhangi bir hata oluştuysa, son Adler-32 toplam hesaplamak ve konsol toplamına yazdırın.  
  
 [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 Aşağıdaki örnek eksiksiz BasicAgent.cpp dosyasını gösterir.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 [[Üst](#top)]  
  
## <a name="sample-input"></a>Örnek Giriş  
 Giriş dosyası text.txt örnek içeriği şudur:  
  
```Output  
The quick brown fox  
jumps  
over the lazy dog  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
 Örnek giriş ile kullanıldığında, bu program şu çıkışı üretir:  
  
```Output  
Adler-32 sum is fefb0d75  
```  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Veri üyeleri için eş zamanlı erişimi engellemek için iş gerçekleştiren yöntemleri eklemenizi öneririz `protected` veya `private` sınıfınızın bölümü. Yalnızca ileti Aracısı bilgisayardan veya gönderip yöntemleri eklemek `public` sınıfınızın bölümü.  
  

 Her zaman çağrısı [concurrency::agent:: Bitti](reference/agent-class.md#done) tamamlandı durumuna aracınızı taşıma yöntemi. Gelen döndürmeden önce genellikle bu yöntemi çağırabilmeniz `run` yöntemi.  

  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bir aracı temelli uygulama başka bir örnek için bkz [izlenecek yol: kilitlenmeyi önlemek için birleştirme birleşim kullanılarak](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)   
 [Eşitleme veri yapıları](../../parallel/concrt/synchronization-data-structures.md)   
 [İzlenecek Yol: Kilitlenmeyi Önlemek için birleştirme kullanma](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)


---
title: 'İzlenecek yol: kilitlenmeyi önlemek için birleştirme birleştirme kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5deb501cc05c2a771b6e14d5091b1baa95f2f622
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693355"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>İzlenecek yol: Kilitlenmeyi Önlemek için birleştirme kullanma
Bu konuda yemek Yiyen Filozoflar sorunu nasıl kullanılacağını göstermek için kullanır. [concurrency::join](../../parallel/concrt/reference/join-class.md) uygulamanızda kilitlenmeyi önlemek için sınıf. Bir yazılım uygulamasında *kilitlenme* iki veya daha çok işlemler her bir kaynak basılı tutun ve karşılıklı olarak başka bir kaynağın serbest bırakmak başka bir işlemin tamamlanmasını beklemek oluşur.  
  
 Yemek Yiyen Filozoflar sorunu, bir kaynak kümesi birden çok eşzamanlı işlemler arasında paylaşılan oluşabilecek sorunları genel kümesinin belirli bir örnektir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki konuları okuyun:  
  
- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)  
  
- [İzlenecek Yol: Aracı Temelli Uygulama Oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)  
  
- [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Bölümler  
 Bu kılavuz aşağıdaki bölümleri içerir:  
  
- [Yemek Yiyen Filozoflar sorunu](#problem)  
  
- [Naïve uygulama](#deadlock)  
  
- [Birleşim kilitlenmeyi önlemek için birleştirme kullanma](#solution)  
  
##  <a name="problem"></a> Yemek Yiyen Filozoflar sorunu  
 Yemek Yiyen Filozoflar sorunu kilitlenme bir uygulamada nasıl gerçekleştiğini gösterir. Bu sorun, beş Yiyen Filozoflar bir gidiş tablosunda sit. Her filozof beslenme ve düşünüyorum arasında geçiş yapar. Her filozof ile komşu sola ve başka bir chopstick paylaşmalıdır chopstick sağındaki komşu ile. Aşağıdaki çizimde, bu düzeni gösterilir.  
  
 ![Yemek Yiyen Filozoflar sorunu](../../parallel/concrt/media/dining_philosophersproblem.png "dining_philosophersproblem")  
  
 Yemek için bir filozof iki chopsticks tutmanız gerekir. Her filozof tek chopstick tutar ve için başka bir bekleyen, ardından hiçbir filozof yemek ve tüm tamamen Kaynaksız bırakabilir.  
  
 [[Üst](#top)]  
  
##  <a name="deadlock"></a> Naïve uygulama  
 Aşağıdaki örnek yemek Yiyen Filozoflar sorunu naïve uyarlamasını gösterir. `philosopher` Türeyen sınıf [concurrency::agent](../../parallel/concrt/reference/agent-class.md), bağımsız olarak davranacak şekilde her filozof sağlar. Paylaşılan bir dizi örnek kullanır [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) her vermek için nesneleri `philosopher` nesne chopsticks çiftinin özel erişim.  
  
 Çizim, kullanımla ilgili `philosopher` sınıfı, bir filozof temsil eder. Bir `int` değişken her chopstick temsil eder. `critical_section` Nesneleri üzerinde chopsticks rest sahipleri hizmet eder. `run` Yöntemi filozof ömrünü benzetimini yapar. `think` Yöntemi düşünmeye act taklit eder ve `eat` yöntemi beslenme eylemi benzetimini yapar.  
  
 A `philosopher` nesne kilitler her ikisi de `critical_section` sahiplerini kendisinden önce gelen chopsticks kaldırılmasını benzetimini gerçekleştirmek için çağırdığı nesneleri `eat` yöntemi. Çağrısından sonra `eat`, `philosopher` nesnesi döndüren chopsticks üstlenenlere ayarlayarak `critical_section` nesneleri geri kilidi durumu.  
  
 `pickup_chopsticks` Yöntemi kilitlenme gerçekleşebileceği göstermektedir. Her varsa `philosopher` nesne kilitler birini ve ardından Hayır erişim kazanır `philosopher` diğer kilidi başkası tarafından kontrol edilir çünkü nesne devam edebilir `philosopher` nesnesi.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
  
### <a name="code"></a>Kod  
 [!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `philosophers-deadlock.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc Yiyen Filozoflar-deadlock.cpp**  
  
 [[Üst](#top)]  
  
##  <a name="solution"></a> Birleşim kilitlenmeyi önlemek için birleştirme kullanma  
 Bu bölümde, ileti arabelleklerinin ve ileti geçirme işlevleri kilitlenme olasılığını ortadan kaldırmak için nasıl kullanılacağını gösterir.  
  
 Bu örnek önceki bir ilişkilendirmek için `philosopher` sınıfı değiştirir her `critical_section` kullanarak nesne bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) nesne ve `join` nesne. `join` Filozof chopsticks sağlayan bir arbiter nesne görür.  
  
 Bu örnekte `unbounded_buffer` ne zaman bir hedef iletiden aldığından sınıfı bir `unbounded_buffer` nesnesi, iletiyi, ileti kuyruğundan kaldırılır. Böylece bir `unbounded_buffer` olduğunu belirten bir ileti chopstick tutan nesnenin kullanılabilir. Bir `unbounded_buffer` hiçbir ileti tutan nesnesini gösterir chopstick kullanılıyor.  
  
 Bu örnek bir doyumsuz olmayan kullanır `join` doyumsuz olmayan birleştirme her verdiğinden nesne `philosopher` nesne hem chopsticks erişimi yalnızca her ikisi de `unbounded_buffer` nesneleri içeren bir ileti. Kullanılabilir durumda olduklarında hemen doyumsuz birleştirme iletileri kabul ettiğinden doyumsuz birleştirme kilitlenme engellemeyecek. Kilitlenme gerçekleşebilir tüm doyumsuz `join` nesneler iletilerinden birini alabilirsiniz ancak sonsuza kadar diğer için kullanılabilir olmasını bekleyin.  
  
 Doyumsuz ve doyumsuz olmayan birleştirmeler ve çeşitli ileti arabellek türleri arasındaki farklar hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).  
  
#### <a name="to-prevent-deadlock-in-this-example"></a>Bu örnekte kilitlenmeyi önlemek için  
  
1.  Aşağıdaki kod örnekten kaldırın.  
  
 [!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]  
  
2.  Türünü değiştirme `_left` ve `_right` veri üyeleri `philosopher` sınıfının `unbounded_buffer`.  
  
 [!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]  
  
3.  Değiştirme `philosopher` yapılacak Oluşturucusu `unbounded_buffer` nesneleri parametreleri olarak.  
  
 [!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]  
  
4.  Değiştirme `pickup_chopsticks` bir doyumsuz olmayan kullanılacak yöntemi `join` hem chopsticks ileti arabelleklerinin iletileri alacak şekilde nesnesi.  
  
 [!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]  
  
5.  Değiştirme `putdown_chopsticks` hem chopsticks ileti arabelleklerinin bir ileti göndererek chopsticks erişimi yayımlamayı yöntemi.  
  
 [!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]  
  
6.  Değiştirme `run` sonuçlarını tutacak yöntemi `pickup_chopsticks` yöntemi ve bu sonuçlar geçirmek için `putdown_chopsticks` yöntemi.  
  
 [!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]  
  
7.  Bildirimi değiştirme `chopsticks` değişkeni `wmain` işlevin bir dizi olmasını `unbounded_buffer` nesneleri her bir ileti tutun.  
  
 [!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kullanan tamamlanan örnek doyumsuz olmayan gösterir `join` kilitlenme riski ortadan kaldırmak için nesne.  
  
### <a name="code"></a>Kod  
 [!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnek şu çıkışı üretir.  
  
```Output  
aristotle ate 50 times.  
descartes ate 50 times.  
hobbes ate 50 times.  
socrates ate 50 times.  
plato ate 50 times.  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `philosophers-join.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc Yiyen Filozoflar-join.cpp**  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)   
 [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

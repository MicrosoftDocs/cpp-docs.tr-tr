---
title: 'Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: f5d48b68d03adc25cd5f87122591b52e37da700a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219605"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma

Fazla abonelik, yüksek miktarda gecikme süresi olan görevleri içeren bazı uygulamaların genel verimliliğini iyileştirebilir. Bu konuda, bir ağ bağlantısından veri okunmasından kaynaklanan gecikmeyi kaydırmak için fazla abonelik kullanımı gösterilmektedir.

## <a name="example"></a>Örnek

Bu örnek, HTTP sunucularından dosya indirmek için [zaman uyumsuz aracılar kitaplığını](../../parallel/concrt/asynchronous-agents-library.md) kullanır. `http_reader`Sınıfı [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) öğesinden TÜRETILIR ve hangi URL adlarının indirileceği zaman uyumsuz olarak okumak için ileti geçirme kullanır.

`http_reader`Sınıfı, her dosyayı eşzamanlı olarak okumak için [concurrency:: task_group](reference/task-group-class.md) sınıfını kullanır. Her görev, geçerli bağlamda fazla aboneliği etkinleştirmek için olarak ayarlanan parametresi ile [concurrency:: Context:: Oversubscribe](reference/context-class.md#oversubscribe) yöntemini çağırır `_BeginOversubscription` **`true`** . Sonra her bir görev, dosyayı indirmek için Microsoft Foundation Sınıfları (MFC) [CInternetSession](../../mfc/reference/cinternetsession-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) sınıflarını kullanır. Son olarak, her görev, `Context::Oversubscribe` `_BeginOversubscription` **`false`** fazla aboneliği devre dışı bırakmak için olarak ayarlanmış parametresi ile çağırır.

Fazla abonelik etkin olduğunda, çalışma zamanı görevlerin çalıştırılacağı bir ek iş parçacığı oluşturur. Bu iş parçacıklarının her biri, geçerli bağlamın üzerine de abone olabilir ve bu nedenle ek iş parçacıkları oluşturabilir. `http_reader`Sınıfı, uygulamanın kullandığı iş parçacığı sayısını sınırlandırmak için bir [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi kullanır. Aracı, arabelleği sabit sayıda belirteç değeri ile başlatır. Her bir indirme işlemi için, aracı, işlem başlamadan önce arabellekteki bir belirteç değeri okur ve sonra işlem bittikten sonra bu değeri arabelleğe geri yazar. Arabellek boş olduğunda, aracı indirme işlemlerinden birinin bir değeri arabelleğe geri yazmasını bekler.

Aşağıdaki örnek, eşzamanlı görevlerin sayısını, kullanılabilir donanım iş parçacıklarının sayısı iki katına kısıtlar. Bu değer, aşırı abonelik ile denemeler yaparken kullanmak için iyi bir başlangıç noktasıdır. Belirli bir işleme ortamına uygun bir değer kullanabilir veya gerçek iş yüküne yanıt vermek için dinamik olarak bu değeri değiştirebilirsiniz.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

Bu örnek, dört işlemcili bir bilgisayarda aşağıdaki çıktıyı üretir:

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

Diğer görevler, bir görünmeyen işlemin tamamlanmasını beklerken ek görevler çalıştığından, bu örnek daha hızlı çalışabilir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `download-oversubscription.cpp` ve sonra bir **Visual Studio komut istemi** penceresinde aşağıdaki komutlardan birini çalıştırın.

```cmd
cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp
cl.exe /EHsc /MT download-oversubscription.cpp
```

## <a name="robust-programming"></a>Güçlü Programlama

Artık gerek kalmadığında fazla aboneliği devre dışı bırakın. Başka bir işlev tarafından oluşturulan bir özel durumu işlemeyen bir işlev düşünün. İşlev döndürülmadan önce fazla abonelik devre dışı bırakıldıysanız, diğer paralel işler de geçerli bağlamın üzerine abone olur.

Fazla aboneliği verilen bir kapsama sınırlamak için *kaynak alımı başlatma* (rampa) modelini kullanabilirsiniz. OYıı deseninin altında, yığın üzerinde bir veri yapısı ayrılır. Bu veri yapısı oluşturulduğunda bir kaynağı başlatır veya alır ve veri yapısı yok edildiğinde bu kaynağı yok eder veya serbest bırakır. RAMPALAMA kapsamı, yok edicinin kapsayan kapsam gelmeden önce çağrıldığından emin olur. Bu nedenle, bir özel durum oluştuğunda veya bir işlev birden çok deyim içerdiğinde kaynak doğru bir şekilde yönetilir **`return`** .

Aşağıdaki örnek adlı bir yapıyı tanımlar `scoped_blocking_signal` . Yapının Oluşturucusu, `scoped_blocking_signal` aşırı abonelik ve yok edici fazla aboneliği devre dışı bırakır.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

Aşağıdaki örnek, `download` işlevin dönüşünden önce aşırı aboneliğin devre dışı olduğundan emin olmak için, metodun gövdesini, SII 'yi kullanacak şekilde değiştirir. Bu teknik, `download` yöntemin özel durum açısından güvenli olmasını sağlar.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bağlamlar](../../parallel/concrt/contexts.md)<br/>
[Context:: Oversubscribe yöntemi](reference/context-class.md#oversubscribe)

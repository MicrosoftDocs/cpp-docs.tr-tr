---
title: 'Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: 02c72e7b7f0e3ec9727504d62341d945dcd0d957
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141945"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma

Fazla abonelik, yüksek miktarda gecikme süresi olan görevleri içeren bazı uygulamaların genel verimliliğini iyileştirebilir. Bu konuda, bir ağ bağlantısından veri okunmasından kaynaklanan gecikmeyi kaydırmak için fazla abonelik kullanımı gösterilmektedir.

## <a name="example"></a>Örnek

Bu örnek, HTTP sunucularından dosya indirmek için [zaman uyumsuz aracılar kitaplığını](../../parallel/concrt/asynchronous-agents-library.md) kullanır. `http_reader` sınıfı [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) ' den türetilir ve indirilecek URL adlarını zaman uyumsuz olarak okumak için ileti geçişini kullanır.

`http_reader` sınıfı, her dosyayı eşzamanlı olarak okumak için [concurrency:: task_group](reference/task-group-class.md) sınıfını kullanır. Her görev, geçerli bağlamda fazla aboneliği etkinleştirmek için `_BeginOversubscription` parametresi **true** olarak ayarlanan [concurrency:: Context:: Oversubscribe](reference/context-class.md#oversubscribe) yöntemini çağırır. Sonra her bir görev, dosyayı indirmek için Microsoft Foundation Sınıfları (MFC) [CInternetSession](../../mfc/reference/cinternetsession-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) sınıflarını kullanır. Son olarak, her görev, aşırı aboneliği devre dışı bırakmak için `_BeginOversubscription` parametresi **false** olarak ayarlanmış `Context::Oversubscribe` çağırır.

Fazla abonelik etkin olduğunda, çalışma zamanı görevlerin çalıştırılacağı bir ek iş parçacığı oluşturur. Bu iş parçacıklarının her biri, geçerli bağlamın üzerine de abone olabilir ve bu nedenle ek iş parçacıkları oluşturabilir. `http_reader` sınıfı, uygulamanın kullandığı iş parçacıklarının sayısını sınırlandırmak için bir [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi kullanır. Aracı, arabelleği sabit sayıda belirteç değeri ile başlatır. Her bir indirme işlemi için, aracı, işlem başlamadan önce arabellekteki bir belirteç değeri okur ve sonra işlem bittikten sonra bu değeri arabelleğe geri yazar. Arabellek boş olduğunda, aracı indirme işlemlerinden birinin bir değeri arabelleğe geri yazmasını bekler.

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

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `download-oversubscription.cpp` adlı bir dosyaya yapıştırın ve sonra bir **Visual Studio komut istemi** penceresinde aşağıdaki komutlardan birini çalıştırın.

```cmd
cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp
cl.exe /EHsc /MT download-oversubscription.cpp
```

## <a name="robust-programming"></a>Güçlü Programlama

Artık gerek kalmadığında fazla aboneliği devre dışı bırakın. Başka bir işlev tarafından oluşturulan bir özel durumu işlemeyen bir işlev düşünün. İşlev döndürülmadan önce fazla abonelik devre dışı bırakıldıysanız, diğer paralel işler de geçerli bağlamın üzerine abone olur.

Fazla aboneliği verilen bir kapsama sınırlamak için *kaynak alımı başlatma* (rampa) modelini kullanabilirsiniz. OYıı deseninin altında, yığın üzerinde bir veri yapısı ayrılır. Bu veri yapısı oluşturulduğunda bir kaynağı başlatır veya alır ve veri yapısı yok edildiğinde bu kaynağı yok eder veya serbest bırakır. RAMPALAMA kapsamı, yok edicinin kapsayan kapsam gelmeden önce çağrıldığından emin olur. Bu nedenle, bir özel durum oluştuğunda veya bir işlev birden çok `return` deyimi içerdiğinde kaynak doğru bir şekilde yönetilir.

Aşağıdaki örnek, `scoped_blocking_signal`adlı bir yapıyı tanımlar. `scoped_blocking_signal` yapısının Oluşturucusu fazla aboneliği ve yok edici fazla aboneliği devre dışı bırakır.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

Aşağıdaki örnek, işlev döndürülmadan önce aşırı aboneliğin devre dışı olduğundan emin olmak için `download` yönteminin gövdesini değiştirerek SII 'yi kullanır. Bu teknik, `download` yönteminin özel durum açısından güvenli olmasını sağlar.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bağlamlar](../../parallel/concrt/contexts.md)<br/>
[Context:: Oversubscribe yöntemi](reference/context-class.md#oversubscribe)

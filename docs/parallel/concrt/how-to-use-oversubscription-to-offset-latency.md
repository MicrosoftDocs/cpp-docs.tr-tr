---
title: 'Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: fc16fa5cfeddf82b9fcb0164796fb7f4c90aef15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653082"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma

Aşırı abonelik gecikme süresi yüksek miktarda sahip görevleri içeren bazı uygulamaları genel verimliliğini artırabilir. Bu konuda, bir ağ bağlantısından veri okuyarak neden dengelemek için aşırı abonelik kullanma gösterilmektedir.

## <a name="example"></a>Örnek

Bu örnekte [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) HTTP sunuculardan dosyaları indirilemedi. `http_reader` Sınıf türetilir [concurrency::agent](../../parallel/concrt/reference/agent-class.md) ve ileti geçirme indirmek için hangi URL adlarını zaman uyumsuz olarak okumak için kullanır.

`http_reader` Sınıfının kullandığı [concurrency::task_group](reference/task-group-class.md) eşzamanlı olarak her dosyayı okumak için sınıf. Her görev çağırır [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) yöntemiyle `_BeginOversubscription` parametresini **true** geçerli bağlamda gecikmeyi etkinleştirmek için. Her görev, ardından Microsoft Foundation Classes (MFC) kullanan [Cınternetsession](../../mfc/reference/cinternetsession-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) dosyasını indirmek için sınıflar. Son olarak, her görev çağırır `Context::Oversubscribe` ile `_BeginOversubscription` parametresini **false** aşırı abonelik devre dışı bırakmak için.

Aşırı abonelik etkin olduğunda, çalışma zamanı, görevleri çalıştırmak için ek bir iş parçacığı oluşturur. Her bu iş parçacığı sayısı ayrıca geçerli bağlam oversubscribe ve böylece ek iş parçacığı oluşturma. `http_reader` Sınıfını kullanan bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) uygulamanın kullandığı iş parçacıklarının sayısını sınırlamak için nesne. Aracıyı arabellek belirteci değerleri sabit sayıda ile başlatır. İşlemi başlatır ve işlem tamamlandıktan sonra sonra bu değeri geri arabelleğe Yazar önce her bir yükleme işlemi için aracı arabellekteki belirteç değeri okur. Arabellek boş olduğunda, bir değer geri arabelleğe yazmak için indirme işlemlerinin biri için aracının bekler.

Aşağıdaki örnek, kullanılabilir donanım iş parçacıklarının sayısını iki kez eşzamanlı görevlere sayısını sınırlar. Aşırı abonelik ile denemeler yapılırken kullanılacak iyi bir başlangıç noktası değerdir. Bu değer gerçek iş yüküne yanıt vermek için dinamik olarak değiştirmenize ya da belirli bir işlem ortamı uygun bir değer kullanın.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

Bu örnekte, dört işlemciye sahip bir bilgisayarda aşağıdaki çıktıyı üretir:

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

Örnek, diğer görevler görünmeyen bir işlemin tamamlanmasını beklerken ek görevleri çalıştırmak için aşırı abonelik etkin olduğunda daha hızlı bir şekilde çalıştırabilirsiniz.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `download-oversubscription.cpp` ve çalışma birini, ardından komutlarını bir **Visual Studio komut istemi** penceresi.

**cl.exe/ehsc/MD /D "_AFXDLL" indirme-oversubscription.cpp**

**cl.exe/ehsc/MT indirme-oversubscription.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Artık gerekli sonra her zaman aşırı abonelik devre dışı bırakın. Başka bir işlev tarafından oluşturulan bir özel durum işlemez bir işlev göz önünde bulundurun. İşlev döndürmeden önce aşırı abonelik devre dışı bırakmayın, herhangi bir ek paralel çalışma da geçerli bağlam oversubscribe.

Kullanabileceğiniz *olduğu kaynak alımı başlatma* (RAII) düzeni, belirli bir kapsama gecikmeyi sınırlamak için. RAII deseni altında bir veri yapısı yığında ayrılır. Bu veri yapısını başlatır veya bir kaynak oluşturulur ve yok eder veya veri yapısı kaldırıldığında bu kaynağı yayınlar zaman alır. RAII deseni kapsayan kapsam çıkar önce yok Edicisi çağrılır garanti eder. Bu nedenle, kaynağın doğru bir özel durum oluştuğunda ya da birden çok işlev içerdiğinde, yönetilen `return` deyimleri.

Aşağıdaki örnekte adlı bir yapı tanımlar `scoped_blocking_signal`. Oluşturucusuna `scoped_blocking_signal` yapısı gecikmeyi sağlar ve yok edici aşırı abonelik devre dışı bırakır.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

Aşağıdaki örnek gövdesinin değiştirir `download` işlevi döndürmeden önce bu gecikmeyi emin olmak için RAII kullanılacak yöntemi devre dışıdır. Bu teknik sağlar `download` özel durum açısından güvenli bir yöntemdir.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlamlar](../../parallel/concrt/contexts.md)<br/>
[Context::Oversubscribe yöntemi](reference/context-class.md#oversubscribe)


---
title: "Nasıl yapılır: gecikmeyi dengelemek için aşırı abonelik kullanma | Microsoft Docs"
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
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1a8f059abffd261de2002ed5d18067c48d74876
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma
Aşırı abonelik gecikme yüksek miktarda olan görevler içeren bazı uygulamaları genel verimliliğini artırabilir. Bu konuda, bir ağ bağlantısından veri okuyarak neden gecikmeyi dengelemek için aşırı abonelik kullanma gösterilmektedir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) HTTP sunucularından dosyalarını indirmek için. `http_reader` Sınıfı türer [concurrency::agent](../../parallel/concrt/reference/agent-class.md) ve ileti geçirme indirmek için hangi URL adlarını zaman uyumsuz olarak okumak için kullanır.  
  
 `http_reader` Sınıfını kullanan [concurrency::task_group](reference/task-group-class.md) eşzamanlı olarak her dosyayı okumak için sınıf. Her görev çağırır [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) yöntemiyle `_BeginOversubscription` parametre kümesine `true` aşırı abonelik geçerli bağlamda etkinleştirmek için. Her görev sonra Microsoft Foundation sınıfları (MFC) kullanan [CInternetSession](../../mfc/reference/cinternetsession-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) dosyasını karşıdan yüklemek için sınıflar. Son olarak, her görevin çağırır `Context::Oversubscribe` ile `_BeginOversubscription` parametre kümesine `false` aşırı abonelik devre dışı bırakmak için.  
  
 Aşırı abonelik etkin olduğunda, çalışma zamanı görevleri çalıştırmak için ek bir iş parçacığı oluşturur. Her bu iş parçacıklarının geçerli bağlamı da oversubscribe ve böylece ek iş parçacığı oluşturma. `http_reader` Sınıfını kullanan bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) uygulamanın kullandığı iş parçacıklarının sayısını sınırlamak için nesne. Aracı simge değerlerini sabit sayıda arabellekle başlatır. İşlemi başlatır ve işlem tamamlandıktan sonra sonra bu değeri geri arabelleğe Yazar önce her bir indirme işlemi için bir belirteç değeri aracı arabelleğinden okur. Arabellek boş olduğunda, bir değeri geri arabelleğe yazmak için indirme işlemlerinin Aracısı bekler.  
  
 Aşağıdaki örnekte, kullanılabilir donanım iş parçacığı sayısını iki kez eşzamanlı görevlere sayısını sınırlar. Bu değer ile aşırı abonelik denerken, kullanmak için iyi bir başlangıç noktası olur. Belirli işleme ortamı uygun bir değer kullanın veya dinamik olarak gerçek iş yükü için yanıt vermek için bu değeri değiştirebilirsiniz.  
  
 [!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]  
  
 Bu örnek, dört işlemciye sahip bir bilgisayarda şu çıkışı üretir:  
  
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
  
 Aşırı abonelik diğer görevleri tamamlamak görünmeyen bir işlemi için beklerken ek görevleri çalıştırmak için etkinleştirildiğinde, örnek daha hızlı çalıştırabilirsiniz.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `download-oversubscription.cpp` ve ardından bir Visual Studio komut istemi penceresinde aşağıdaki çalışma biri komutları.  
  
 **cl.exe /EHsc /MD /D "_AFXDLL" indirme-oversubscription.cpp**  
  
 **cl.exe /EHsc/MT indirme-oversubscription.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Her zaman artık gerek sonra aşırı abonelik devre dışı bırakın. Başka bir işlev tarafından oluşturulan bir özel durum işlemedi bir işlev göz önünde bulundurun. İşlev döndürmeden önce aşırı abonelik devre dışı bırakmayın, ek bir paralel iş de geçerli bağlamı oversubscribe.  
  
 Kullanabileceğiniz *kaynak edinme olan başlatma* aşırı abonelik belirli bir kapsama sınırlamak için (RAII) desen. RAII deseni altında bir veri yapısı yığında ayrılmış. Bu veri yapısını başlatır veya bir kaynak oluşturulur ve bozar veya veri yapısı kaldırıldığı zaman, kaynak serbest zaman alır. RAII deseni çevreleyen kapsamdaki çıkar önce yıkıcı adlandırılır güvence altına alır. Bu nedenle, kaynak doğru bir özel durum oluştuğunda veya birden çok işlev içerdiğinde, yönetilen `return` deyimleri.  
  
 Aşağıdaki örnek adlı bir yapıyı tanımlayan `scoped_blocking_signal`. Oluşturucusunun `scoped_blocking_signal` yapısı aşırı abonelik sağlar ve yıkıcı aşırı abonelik devre dışı bırakır.  
  
 [!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]  
  
 Aşağıdaki örnek gövdesini değiştirir `download` işlevi döndürmeden önce bu aşırı abonelik emin olmak için RAII kullanılacak yöntemi devre dışı. Bu teknik sağlar `download` özel durum güvenli bir yöntemdir.  
  
 [!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlamları](../../parallel/concrt/contexts.md)   
 [Context::Oversubscribe yöntemi](reference/context-class.md#oversubscribe)



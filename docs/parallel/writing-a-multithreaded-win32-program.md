---
title: "Çoklu iş parçacığı kullanan Win32 programı yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- thread stacks [C++]
- resources [C++], multithreading
- stacks [C++]
- shared resources [C++]
- threading [C++], sharing common resources
- multithreading [C++], thread stacks
- multithreading [C++], sharing common resources
- mutual exclusion [C++]
- communications [C++], between threads
- mutex [C++]
- threading [C++], thread stacks
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ede0e6dc1740f93f4905dc69b1927aee0d1a7ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-a-multithreaded-win32-program"></a>Çoklu İş Parçacığı Kullanan Win32 Programı Yazma
Birden çok iş parçacığı sahip bir program yazdığınızda, davranışlarını koordine gerekir ve [programın kaynaklarının kullanımını](#_core_sharing_common_resources_between_threads). Ayrıca her iş parçacığı aldığından emin olmak gerekir [kendi yığını](#_core_thread_stacks).  
  
##  <a name="_core_sharing_common_resources_between_threads"></a>İş parçacıkları arasında ortak kaynakları paylaşma  
  
> [!NOTE]
>  MFC açısından benzer hakkında bilgi için bkz [çoklu iş parçacığı kullanımı: programlama ipuçları](../parallel/multithreading-programming-tips.md) ve [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma zamanı](../parallel/multithreading-when-to-use-the-synchronization-classes.md).  
  
 Her iş parçacığı kendi yığınına sahiptir ve CPU kopyasını kaydeder. Dosyaları, statik verileri ve yığın bellek gibi başka kaynaklar işlemin tüm iş parçacıkları tarafından paylaşılır. Bu ortak kaynakları kullanarak iş parçacıklarını eşitlenmelidir. Win32 semafor, kritik bölümler, olayları ve zaman uyumu sağlayıcılar dahil kaynakları eşitlemek için çeşitli yöntemler sağlar.  
  
 Birden çok iş parçacığı statik verilere erişirken programınız için olası kaynak çakışması sağlamanız gerekir. Burada bir iş parçacığı güncelleştirmeleri içeren bir statik veri yapısı bir program dikkate *x*,*y* başka bir iş parçacığı tarafından görüntülenecek öğeleri koordinatları. Güncelleştirme iş parçacığı değiştirirse *x* koordine etmek ve değiştirebilmek için önce etkisiz *y* koordinat, görüntüleme iş parçacığı önce zamanlanmış olabileceğinden *y* koordinat değil güncelleştirildi. Öğe yanlış konumunda görüntülenir. Bu sorunu yapısı erişimi denetlemek için semafor kullanarak önleyebilirsiniz.  
  
 Bir mutex (kısaltması *mut*ual *ex*clusion) iş parçacıkları veya başka zaman uyumsuz olarak yürütülen işlemler arasında iletişim kurulurken bir yoludur. Bu iletişim, genellikle bir paylaşılan kaynağa erişim kilitleme ve kaynağın kilidini açma denetleyerek etkinlikleri, birden çok iş parçacığı veya işlemler, genellikle koordine etmek için kullanılır. Bunu çözmek için *x*,*y* koordinat güncelleme sorununu, güncelleştirme iş parçacığı veri yapısı güncelleştirme gerçekleştirmeden önce kullanımda olduğunu belirten bir mutex ayarlar. Her iki koordinatları işlenmiş sonra onu mutex'i temizler. Görüntüleme iş parçacığı görüntülemeyi güncellemeden önce temizlenmesini mutex beklemeniz gerekir. Bu işlem için bir mutex bekleniyor, çoğunlukla işlemi engellenir ve mutex temizlenene kadar devam edemez çünkü dışlamada engelleme adı verilir.  
  
 Gösterilen Bounce.c programı [örnek çoklu iş parçacığı kullanan C programı](../parallel/sample-multithread-c-program.md) adlı bir mutex kullanır `ScreenMutex` ekran güncelleştirmelerini koordine etmek için. Görüntü iş parçacığı birini hazır ekranına yazmak her zaman çağırır **WaitForSingleObject** tanıtıcısını ile `ScreenMutex` ve sabit **SONSUZ** belirtmek için  **WaitForSingleObject** çağrısı bloğu mutex ve zaman aşımına üzerinde. Varsa `ScreenMutex` bekleme işlevi başka bir iş parçacığı ekranıyla böylece mutex ayarlar ve iş parçacığının devam ettirir. Aksi takdirde mutex temizlenene kadar iş parçacığı engeller. İş parçacığı görünen güncelleştirme tamamlandığında çağırarak mutex serbest **ReleaseMutex**.  
  
 Ekran görüntüleri ve statik verileri yalnızca dikkatli yönetim gerektiren kaynaklara ikisidir. Örneğin, programınızı aynı dosyaya erişen birden çok iş parçacığı sayısı olabilir. Başka bir iş parçacığı dosya işaretçisini taşınmış çünkü her iş parçacığı dosya işaretçisini okunurken veya yazılırken önce sıfırlamanız gerekir. Ayrıca, her iş parçacığı, işaretçi konumlandırır zaman ve dosyaya eriştiği zaman arasında geçersiz kılınırsa değil, emin olmanız gerekir. Bu iş parçacıkları ile her dosya erişimi köşeli ayraç kullanarak dosyaya erişim koordine etmek için semafor kullanması gereken **WaitForSingleObject** ve **ReleaseMutex** çağrıları. Aşağıdaki kod örneği, bu teknik gösterilmektedir:  
  
```  
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);  
  
WaitForSingleObject( hIOMutex, INFINITE );  
fseek( fp, desired_position, 0L );  
fwrite( data, sizeof( data ), 1, fp );  
ReleaseMutex( hIOMutex);  
```  
  
##  <a name="_core_thread_stacks"></a>İş parçacığı yığınları  
 Bir uygulamanın varsayılan yığın alanı tümünün ilk iş parçacığı 1 olarak bilinen yürütme iş parçacığı için ayrılır. Sonuç olarak, her ek iş parçacığı için ayrı bir yığın programınızı ayırmak için ne kadar bellek gerektiriyor belirtmeniz gerekir. Gerekirse ek yığın alanı işletim sistemi için iş parçacığı, ayırır, ancak varsayılan bir değer belirtmeniz gerekir.  
  
 İlk bağımsız değişkeninde `_beginthread` çağrıdır gösteren bir işaretçi **BounceProc** iş parçacığını yürüten işlev. İkinci bağımsız değişkeni iş parçacığı için varsayılan yığın boyutunu belirtir. Son bağımsız değişken için geçirilen bir kimlik numarasıdır **BounceProc**. **BounceProc** rastgele sayı üreticisinin çekirdek ve iş parçacığının renk özniteliği seçin ve karakter görüntülemek için kimlik numarasını kullanır.  
  
 C çalışma zamanı kitaplığı veya Win32 API çağrıları yapma iş parçacığı kitaplığı ve bunlar çağrı API işlevleri için yeterli yığın alanı izin vermeniz gerekir. C `printf` işlevi 500 bayttan fazla yığın alanı gerektirir ve Win32 API yordamları çağrılırken 2 K yığın alanı kullanılabilir olması gerekir.  
  
 Her iş parçacığının kendi yığını olduğundan, mümkün olduğunca az statik veri kullanarak veri öğeleri üzerindeki olası çakışmaları önleyebilirsiniz. Bir iş parçacığı özel olabilecek tüm veriler için otomatik yığın değişkenlerini kullanmak için program tasarlayın. Yalnızca genel Bounce.c programındaki zaman uyumu sağlayıcılar ya da başlatıldıktan sonra hiçbir zaman değişiklik değişkenleri değişkenlerdir.  
  
 Win32 ayrıca iş parçacığı yerel depolaması (iş parçacığı başına verileri depolamak için TLS) sağlar. Daha fazla bilgi için bkz: [iş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)
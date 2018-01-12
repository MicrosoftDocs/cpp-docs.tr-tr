---
title: "C++ ve MCF ile çoklu iş parçacığı kullanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], multithreading
- threading [C++], MFC
- worker threads [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], about threading
- CWinThread class, purpose of
- multithreading [C++], MFC
- threading [MFC]
- user interface threads [C++]
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14d076865cd83837e2de218ad0189c037c78cd83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-with-c-and-mfc"></a>C++ ve MCF ile Çoklu İş Parçacığı Kullanımı
Microsoft Foundation Class (MFC) kitaplığı, birden çok iş parçacıklı uygulamalar için destek sağlar. Bu konu işlemleri ve iş parçacığı ve MFC yaklaşımını açıklar için çoklu iş parçacığı kullanımı.  
  
 Bir işlem, bir uygulama yürütme örneğidir. Örneğin, Not Defteri simgesini çift tıklattığınızda, Notepad çalışan bir işlemi başlatın.  
  
 Bir iş parçacığı yürütmeyi bir işlem içinde bir yoludur. Not Defteri'ni başlatın, işletim sisteminin bir işlem oluşturur ve bu işlemin birincil parçacığının başlar. Bu nedenle bu iş parçacığı sonlandırıldığında işlem yapar. Bu birincil iş parçacığı işletim sistemine işlev adresi şeklinde başlatma kodu tarafından sağlanır. Genellikle, bu adresidir **ana** veya `WinMain` sağlanan işlevi.  
  
 İsterseniz, uygulamanızda ek iş parçacığı oluşturabilirsiniz. Bu arka plan veya bakım görevlerinin tamamlanması bekleyin kullanıcıya istemediğinizde işlemek için yapmak isteyebilirsiniz. MFC uygulamalarında tüm iş parçacıkları tarafından temsil edilen [CWinThread](../mfc/reference/cwinthread-class.md) nesneleri. Çoğu durumda, hatta açıkça bu nesneleri oluşturmanız gerekmez; Bunun yerine framework yardımcı işlevini çağırın [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), oluşturan `CWinThread` nesnesi.  
  
 MFC iş parçacığı iki tür ayırt: kullanıcı arabirimi iş parçacıkları ve iş parçacıklarını. Kullanıcı arabirimi iş parçacıkları, yaygın olarak kullanıcı girişini işlemek ve olayları ve kullanıcı tarafından oluşturulan iletileri yanıtlamak için kullanılır. Çalışan iş parçacığı, kullanıcı girişi gerektirmeyen gibi görevler yeniden hesaplama, tamamlamak için yaygın olarak kullanılır. Win32 API iş parçacığı türleri arasında ayrım yapmaz; yalnızca iş parçacığını yürütmek başlayabilmesi için iş parçacığının başlangıç adresini bilmeniz gerekir. MFC özel kullanıcı arabirimi olayları için ileti Pompalama sağlayarak kullanıcı arabirimi iş parçacıkları işler. `CWinApp`öğesinden türetilen bir kullanıcı arabirimi iş parçacığı nesnesi örneği çünkü `CWinThread` ve olayları ve kullanıcı tarafından oluşturulan iletileri işler.  
  
 Özel dikkat burada birden çok iş parçacığı aynı nesneye erişimi gerektirebilir durumlara verilmelidir. [Çoklu iş parçacığı kullanımı: Programlama ipuçları](../parallel/multithreading-programming-tips.md) bu durumlarda doğabilecek sorunları çözmek almak için kullanabileceğiniz teknikleri açıklar. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma nasıl](../parallel/multithreading-how-to-use-the-synchronization-classes.md) tek bir nesne birden çok iş parçacığından erişimi eşitlemek kullanılabilir sınıflarının nasıl kullanılacağını açıklar.  
  
 Yazma ve birden çok iş parçacıklı programlama hata ayıklama, karmaşık ve hassas iş kendiliğinden nesneleri aynı anda birden çok iş parçacığı tarafından erişilemeyen olmak gerekir çünkü değil. Çoklu iş parçacığı kullanımı konuları birden çok iş parçacıklı programlama MFC birden çok iş parçacıklı programınıza yalnızca nasıl kullanılacağını temellerini öğretmek değildir. Visual C++'de bulunan birden çok iş parçacıklı MFC örnekleri birkaç birden çok iş parçacıklı işlevsellik ekleme ve Win32 API'ları MFC tarafından kapsanmayan gösterilmektedir; Ancak, bunlar yalnızca bir başlangıç noktası olacak şekilde tasarlanmıştır.  
  
 İşletim sistemi işlemleri ve iş parçacıklarını nasıl işlediği hakkında daha fazla bilgi için bkz: [işlemleri ve iş parçacıklarını](http://msdn.microsoft.com/library/windows/desktop/ms684841) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Çoklu İş Parçacığı Kullanımı: Kullanıcı Arabirimi İş Parçacıkları Oluşturma](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [Çoklu İş Parçacığı Kullanımı: Çalışan İş Parçacıkları Oluşturma](../parallel/multithreading-creating-worker-threads.md)  
  
-   [Çoklu İş Parçacığı Kullanımı: Eşitleme Sınıflarını Kullanma](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [Çoklu İş Parçacığı Kullanımı: İş Parçacıklarını Sonlandırma](../parallel/multithreading-terminating-threads.md)  
  
-   [Çoklu İş Parçacığı Kullanımı: Programlama İpuçları](../parallel/multithreading-programming-tips.md)  
  
-   [Çoklu İş Parçacığı Kullanımı: Eşitleme Sınıfları Ne Zaman Kullanılır?](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)
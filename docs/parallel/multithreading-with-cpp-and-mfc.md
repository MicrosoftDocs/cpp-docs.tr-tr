---
title: C++ ve MCF ile Çoklu İş Parçacığı Kullanımı
ms.date: 08/27/2018
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
ms.openlocfilehash: bcffc2964d8e15fd47f437366863748175e12622
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258352"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ ve MCF ile Çoklu İş Parçacığı Kullanımı

Microsoft Foundation Class (MFC) kitaplığının çok iş parçacıklı uygulamalar için destek sağlar. Bu konu süreçleri ve iş parçacıkları ve MFC yaklaşımını açıklar çoklu.

Bir işlem, bir uygulamanın yürütme örneğidir. Örneğin, Not Defteri simgesini çift tıkladığınızda, Not Defteri'ni çalıştıran bir işlem başlar.

Bir iş parçacığı bir işlemdeki yürütme yoludur. Not Defteri'ni başlattığınızda, işletim sistemi bir işlem oluşturur ve bu işlemin birincil iş parçacığını yürütmeye başlar. Bu nedenle bu iş parçacığı sonlandığında, işlem yapar. Bu birincil iş parçacığı işletim sistemine işlev adresi biçiminde başlatma kodu tarafından sağlanır. Genellikle, bu adresidir `main` veya `WinMain` sağlanan işlev.

İsterseniz uygulamanızda ek iş parçacıkları oluşturabilirsiniz. Kullanıcının tamamlanmalarını bekleyin istemediğinizde arka plan veya bakım görevlerinin işlenmesi için bunu yapmak isteyebilirsiniz. MFC uygulamalarında tüm iş parçacıkları tarafından temsil edilen [CWinThread](../mfc/reference/cwinthread-class.md) nesneleri. Çoğu durumda, hatta açıkça bu nesneleri oluşturmanız gerekmez; Bunun yerine çerçeve yardımcısı işlevini çağırın [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), oluşturan `CWinThread` nesnesi.

MFC, iki tür iş parçacığını birbirinden ayırır: kullanıcı arabirimi iş parçacıkları ve çalışan iş parçacıkları. Kullanıcı arabirimi iş parçacıkları genellikle kullanıcı girişlerini işler ve olaylarını ve kullanıcı tarafından oluşturulan iletileri yanıtlamak için kullanılır. Çalışan iş parçacıkları genellikle kullanıcı girişi gerektirmeyen görevleri yeniden hesaplama gibi tamamlamak için kullanılır. Win32 API iş parçacığı türleri arasında ayrım yapmaz; yalnızca iş parçacığının yürütmeye başlayabilmesi için onun başlangıç adresini bilmesi gerekir. MFC özel kullanıcı arabirimdeki olaylar için bir ileti pompası sağlayarak kullanıcı arabirimi iş parçacıkları işler. `CWinApp` öğesinden türetildiği için kullanıcı arabirimi iş parçacığı nesnesi örnektir `CWinThread` ve olaylarını ve kullanıcı tarafından oluşturulan iletileri işler.

İçin burada birden fazla iş parçacığı aynı nesneye erişim gerektirebileceği durumlara özellikle dikkat verilmelidir. [Çoklu iş parçacığı kullanımı: Programlama ipuçları](multithreading-programming-tips.md) bu durumlarda doğabilecek sorunları etrafında almak için kullanabileceğiniz teknikleri açıklar. [Çoklu iş parçacığı kullanımı: Eşitleme sınıflarının nasıl kullanılacağını](multithreading-how-to-use-the-synchronization-classes.md) tek bir nesneye birden çok iş parçacığından erişimi senkronize etmek sınıflarının nasıl kullanılacağını açıklar.

Yazma ve hata ayıklama çok iş parçacıklı programlama, karmaşık ve zor bir iş kendiliğinden nesneleri aynı anda birden fazla iş parçacığı tarafından erişilemeyen emin olmanız gerektiğinden değil. Çoklu iş parçacığı kullanımı konuları, birden çok iş parçacıklı programlama MFC çoklu iş parçacığı kullanan programınızda kullanmak nasıl yalnızca ilgili temel bilgileri öğretmez. Visual C++'de bulunan çoklu iş parçacığı kullanan MFC örnekleri birkaç çoklu iş parçacığı kullanan işlev ekleme ve MFC tarafından kapsanmayan Win32 API'ları gösterilmektedir; Ancak, bunlar yalnızca bir başlangıç noktası olacak şekilde tasarlanmıştır.

İşletim sistemi süreçleri ve iş parçacıklarını nasıl işlediği hakkında daha fazla bilgi için bkz. [işlemleri ve iş parçacıklarını](/windows/desktop/ProcThread/processes-and-threads) Windows SDK.

MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Çoklu iş parçacığı kullanımı: Kullanıcı arabirimi iş parçacıkları oluşturma](multithreading-creating-user-interface-threads.md)

- [Çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](multithreading-creating-worker-threads.md)

- [Çoklu iş parçacığı kullanımı: Eşitleme sınıflarını kullanma](multithreading-how-to-use-the-synchronization-classes.md)

- [Çoklu iş parçacığı kullanımı: İş parçacıklarını sonlandırma](multithreading-terminating-threads.md)

- [Çoklu iş parçacığı kullanımı: Programlama ipuçları](multithreading-programming-tips.md)

- [Çoklu iş parçacığı kullanımı: Zaman eşitleme sınıflarını kullanma](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>Ayrıca bkz.

[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)

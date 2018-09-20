---
title: C++ ve MFC ile çoklu iş parçacığı kullanımı | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a57846311fc3332dba0b613ca37a2b5da4368d3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394640"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ ve MCF ile Çoklu İş Parçacığı Kullanımı

Microsoft Foundation Class (MFC) kitaplığının çok iş parçacıklı uygulamalar için destek sağlar. Bu konu süreçleri ve iş parçacıkları ve MFC yaklaşımını açıklar çoklu.

Bir işlem, bir uygulamanın yürütme örneğidir. Örneğin, Not Defteri simgesini çift tıkladığınızda, Not Defteri'ni çalıştıran bir işlem başlar.

Bir iş parçacığı bir işlemdeki yürütme yoludur. Not Defteri'ni başlattığınızda, işletim sistemi bir işlem oluşturur ve bu işlemin birincil iş parçacığını yürütmeye başlar. Bu nedenle bu iş parçacığı sonlandığında, işlem yapar. Bu birincil iş parçacığı işletim sistemine işlev adresi biçiminde başlatma kodu tarafından sağlanır. Genellikle, bu adresidir `main` veya `WinMain` sağlanan işlev.

İsterseniz uygulamanızda ek iş parçacıkları oluşturabilirsiniz. Kullanıcının tamamlanmalarını bekleyin istemediğinizde arka plan veya bakım görevlerinin işlenmesi için bunu yapmak isteyebilirsiniz. MFC uygulamalarında tüm iş parçacıkları tarafından temsil edilen [CWinThread](../mfc/reference/cwinthread-class.md) nesneleri. Çoğu durumda, hatta açıkça bu nesneleri oluşturmanız gerekmez; Bunun yerine çerçeve yardımcısı işlevini çağırın [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), oluşturan `CWinThread` nesnesi.

MFC, iki tür iş parçacığını birbirinden ayırır: kullanıcı arabirimi iş parçacıkları ve çalışan iş parçacıkları. Kullanıcı arabirimi iş parçacıkları genellikle kullanıcı girişlerini işler ve olaylarını ve kullanıcı tarafından oluşturulan iletileri yanıtlamak için kullanılır. Çalışan iş parçacıkları genellikle kullanıcı girişi gerektirmeyen görevleri yeniden hesaplama gibi tamamlamak için kullanılır. Win32 API iş parçacığı türleri arasında ayrım yapmaz; yalnızca iş parçacığının yürütmeye başlayabilmesi için onun başlangıç adresini bilmesi gerekir. MFC özel kullanıcı arabirimdeki olaylar için bir ileti pompası sağlayarak kullanıcı arabirimi iş parçacıkları işler. `CWinApp` öğesinden türetildiği için kullanıcı arabirimi iş parçacığı nesnesi örnektir `CWinThread` ve olaylarını ve kullanıcı tarafından oluşturulan iletileri işler.

İçin burada birden fazla iş parçacığı aynı nesneye erişim gerektirebileceği durumlara özellikle dikkat verilmelidir. [Çoklu iş parçacığı kullanımı: Programlama ipuçları](multithreading-programming-tips.md) bu durumlarda doğabilecek sorunları etrafında almak için kullanabileceğiniz teknikleri açıklar. [Çoklu iş parçacığı kullanımı: eşitleme sınıfları nasıl](multithreading-how-to-use-the-synchronization-classes.md) tek bir nesneye birden çok iş parçacığından erişimi senkronize etmek sınıflarının nasıl kullanılacağını açıklar.

Yazma ve hata ayıklama çok iş parçacıklı programlama, karmaşık ve zor bir iş kendiliğinden nesneleri aynı anda birden fazla iş parçacığı tarafından erişilemeyen emin olmanız gerektiğinden değil. Çoklu iş parçacığı kullanımı konuları, birden çok iş parçacıklı programlama MFC çoklu iş parçacığı kullanan programınızda kullanmak nasıl yalnızca ilgili temel bilgileri öğretmez. Visual C++'de bulunan çoklu iş parçacığı kullanan MFC örnekleri birkaç çoklu iş parçacığı kullanan işlev ekleme ve MFC tarafından kapsanmayan Win32 API'ları gösterilmektedir; Ancak, bunlar yalnızca bir başlangıç noktası olacak şekilde tasarlanmıştır.

İşletim sistemi süreçleri ve iş parçacıklarını nasıl işlediği hakkında daha fazla bilgi için bkz. [işlemleri ve iş parçacıklarını](/windows/desktop/ProcThread/processes-and-threads) Windows SDK.

MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Çoklu İş Parçacığı Kullanımı: Kullanıcı Arabirimi İş Parçacıkları Oluşturma](multithreading-creating-user-interface-threads.md)

- [Çoklu İş Parçacığı Kullanımı: Çalışan İş Parçacıkları Oluşturma](multithreading-creating-worker-threads.md)

- [Çoklu İş Parçacığı Kullanımı: Eşitleme Sınıflarını Kullanma](multithreading-how-to-use-the-synchronization-classes.md)

- [Çoklu İş Parçacığı Kullanımı: İş Parçacıklarını Sonlandırma](multithreading-terminating-threads.md)

- [Çoklu İş Parçacığı Kullanımı: Programlama İpuçları](multithreading-programming-tips.md)

- [Çoklu İş Parçacığı Kullanımı: Eşitleme Sınıfları Ne Zaman Kullanılır?](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)
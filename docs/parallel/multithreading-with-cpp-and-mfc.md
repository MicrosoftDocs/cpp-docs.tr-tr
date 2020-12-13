---
description: 'Hakkında daha fazla bilgi edinin: C++ ve MFC ile çoklu Iş parçacığı'
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
ms.openlocfilehash: a553f6364f52ce8d91e08e3bb5b0e83b48575fdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149818"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ ve MCF ile Çoklu İş Parçacığı Kullanımı

Microsoft Foundation Class (MFC) kitaplığı çok iş parçacıklı uygulamalar için destek sağlar. Bu konuda işlem ve iş parçacıkları ve çoklu iş parçacığı için MFC yaklaşımı açıklanmaktadır.

İşlem, bir uygulamanın yürütülen örneğidir. Örneğin, Not defteri simgesine çift tıkladığınızda Not defteri çalıştıran bir işlem başlatabilirsiniz.

İş parçacığı, bir işlem içindeki yürütmenin yoludur. Not defteri 'ni başlattığınızda, işletim sistemi bir işlem oluşturur ve bu işlemin birincil iş parçacığını yürütmeye başlar. Bu iş parçacığı sonlandırıldığında işlemi yapar. Bu birincil iş parçacığı, işletim sistemine bir işlev adresi biçiminde başlangıç kodu tarafından verilir. Genellikle, `main` `WinMain` sağlanan OR işlevinin adresidir.

İsterseniz uygulamanızda ek iş parçacıkları oluşturabilirsiniz. Kullanıcının tamamlanmasını beklemesini istemediğiniz durumlarda arka plan veya bakım görevlerini işlemek için bunu yapmak isteyebilirsiniz. MFC uygulamalarındaki tüm iş parçacıkları, [CWinThread](../mfc/reference/cwinthread-class.md) nesneleri tarafından temsil edilir. Çoğu durumda, bu nesneleri açıkça oluşturmanız bile gerekmez; Bunun yerine, sizin için nesneyi oluşturan [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)çerçeve yardımcısı işlevini çağırın `CWinThread` .

MFC iki tür iş parçacığını ayırır: Kullanıcı arabirimi iş parçacıkları ve çalışan iş parçacıkları. Kullanıcı arabirimi iş parçacıkları genellikle kullanıcı girişini işlemek ve Kullanıcı tarafından oluşturulan olaylara ve iletilere yanıt vermek için kullanılır. Çalışan iş parçacıkları genellikle, Kullanıcı girişi gerektirmeyen yeniden hesaplama gibi görevleri gerçekleştirmek için kullanılır. Win32 API, iş parçacıklarının türleri arasında ayrım yapmaz; iş parçacığını yürütmeye başlayabilmesi için iş parçacığının başlangıç adresini bilmesi yeterlidir. MFC Kullanıcı arabirimindeki olaylar için bir ileti göndericisi sağlayarak kullanıcı arabirimi iş parçacıklarını özel olarak işler. `CWinApp` , öğesinden türetildiğinden `CWinThread` ve Kullanıcı tarafından oluşturulan olayları ve iletileri işleytiğinden, Kullanıcı arabirimi iş parçacığı nesnesine bir örnektir.

Birden fazla iş parçacığının aynı nesneye erişmesi gerekebilecek durumlara özel dikkat edilmelidir. [Çoklu Iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md) , bu durumlarda oluşabilecek sorunları gidermek için kullanabileceğiniz teknikleri açıklar. [Çoklu Iş parçacığı kullanımı: eşitleme sınıflarını kullanma,](multithreading-how-to-use-the-synchronization-classes.md) birden çok iş parçacığından erişimi tek bir nesneye eşitlemek için kullanılabilen sınıfların nasıl kullanılacağını açıklar.

Birden çok iş parçacıklı programlama yazma ve hata ayıklama, nesneleri aynı anda birden fazla iş parçacığı tarafından erişilmediğinden emin olmanız gerektiğinden, doğal olarak karmaşık ve karmaşık bir alma işlemi olur. Çoklu iş parçacığı oluşturma konuları çok iş parçacıklı programlama ile ilgili temel bilgileri öğretir, yalnızca çoklu iş parçacıklı programınızda MFC 'yi kullanma. Visual C++ bulunan çok iş parçacıklı MFC örnekleri, MFC tarafından dahil edilen birkaç çok iş parçacıklı Işlevselliği ve Win32 API 'Leri eklemeyi gösterir; Ancak, yalnızca bir başlangıç noktası olmak üzere tasarlanmıştır.

İşletim sisteminin işlem ve iş parçacıklarını işleme hakkında daha fazla bilgi için, bkz. Windows SDK [süreçler ve Iş parçacıkları](/windows/win32/ProcThread/processes-and-threads) .

MFC çoklu iş parçacığı desteği hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Çoklu iş parçacığı kullanımı: User-Interface Iş parçacıkları oluşturma](multithreading-creating-user-interface-threads.md)

- [Çoklu iş parçacığı kullanımı: çalışan Iş parçacıkları oluşturma](multithreading-creating-worker-threads.md)

- [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](multithreading-how-to-use-the-synchronization-classes.md)

- [Çoklu iş parçacığı: Iş parçacıklarını sonlandırma](multithreading-terminating-threads.md)

- [Çoklu iş parçacığı kullanımı: programlama Ipuçları](multithreading-programming-tips.md)

- [Çoklu iş parçacığı kullanımı: eşitleme sınıfları ne zaman kullanılır?](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>Ayrıca bkz.

[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)

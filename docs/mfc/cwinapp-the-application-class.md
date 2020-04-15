---
title: 'CWinApp: Uygulama Sınıfı'
ms.date: 11/04/2016
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
ms.openlocfilehash: 007a4e53fd9b3eae612947cd76ee352776572d4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373532"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Uygulama Sınıfı

MFC'deki ana uygulama sınıfı, Windows işletim sistemi için bir uygulamanın başlatılmasını, çalıştırılmasını ve sonlandırılmasını kapsar. Çerçeve üzerine oluşturulmuş bir [uygulama, CWinApp'tan](../mfc/reference/cwinapp-class.md)türetilen bir sınıfın yalnızca bir nesnesi olmalıdır. Bu nesne, pencereler oluşturulmadan önce oluşturulur.

`CWinApp`bir veya `CWinThread`daha fazla iş parçacığı olabilir uygulamanız için yürütme ana iş parçacığı temsil eden türetilmiştir. MFC'nin son `InitInstance`sürümlerinde, `ExitInstance` **Run** `OnIdle` , ve üye `CWinThread`işlevler aslında sınıftadır. Tartışma birincil iş parçacığı yerine `CWinApp` uygulama nesnesi olarak nesnenin rolü ile ilgili olduğundan, bu işlevler burada üye yerine üye gibi tartışılır.

> [!NOTE]
> Uygulama sınıfınız, uygulamanızın birincil yürütme iş parçacığıoluşturur. Win32 API işlevlerini kullanarak ikincil yürütme iş parçacıkları da oluşturabilirsiniz. Bu iş parçacıkları MFC Kitaplığını kullanabilir. Daha fazla bilgi için [Multithreading'e](../parallel/multithreading-support-for-older-code-visual-cpp.md)bakın.

Windows işletim sistemi için herhangi bir program gibi, çerçeve uygulama bir `WinMain` işlevi vardır. Ancak, bir çerçeve uygulamasında, `WinMain`yazmayın. Sınıf kitaplığı tarafından sağlanır ve uygulama başlatıldığında çağrılır. `WinMain`pencere sınıflarını kaydetme gibi standart hizmetleri gerçekleştirir. Daha sonra uygulamayı başlatmave çalıştırmak için uygulama nesnesinin üye işlevlerini çağırır. (Çağıran `CWinApp` üye işlevleri geçersiz kılarak özelleştirebilirsiniz.) `WinMain` `WinMain`

Uygulamayı başlatmayı sağlamak `WinMain` için uygulama nesnenizin `InitApplication` ve `InitInstance` üye işlevlerinizin çağrısını alır. Uygulamanın ileti döngüsüçalıştırmak için `WinMain` **Çalıştır** üye işlevini çağırır. Sonlandırma `WinMain` da, uygulama nesnesinin `ExitInstance` üye işlevini çağırır.

> [!NOTE]
> Bu belgede **kalın** olarak gösterilen adlar, Microsoft Foundation Class Library ve Visual C++ tarafından sağlanan öğeleri gösterir. Türde `monospaced` gösterilen adlar oluşturduğunuz veya geçersiz kıldığınız öğeleri gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CWinApp ve MFC Uygulama Sihirbazı](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[Geçersiz Kılınabilir CWinApp Üye İşlevleri](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)

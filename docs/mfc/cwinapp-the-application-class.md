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
ms.openlocfilehash: 8518e21a9fa6bcf5ac640cff25b17c5028046b06
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447028"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Uygulama Sınıfı

MFC 'deki ana uygulama sınıfı, Windows işletim sistemi için bir uygulamanın başlatılmasını, çalıştırılmasını ve sonlandırılmasını kapsüller. Framework üzerinde oluşturulan bir uygulama, [CWinApp](../mfc/reference/cwinapp-class.md)'dan türetilmiş bir sınıfın bir ve sadece bir nesnesine sahip olmalıdır. Bu nesne Windows oluşturulmadan önce oluşturulur.

`CWinApp`, uygulamanız için yürütmenin ana iş parçacığını temsil eden, bir veya daha fazla iş parçacığına sahip olabilen `CWinThread`türetilir. MFC 'nin son sürümlerinde `InitInstance`, **Çalıştır**, `ExitInstance`ve `OnIdle` üye işlevleri aslında sınıf `CWinThread`. Bu işlevler burada `CWinApp` üye gibi açıklanmıştır, çünkü tartışma nesnenin rolünü birincil iş parçacığı yerine uygulama nesnesi olarak ilgilendirirler.

> [!NOTE]
>  Uygulama sınıfınız, uygulamanızın yürütmenin birincil iş parçacığını oluşturur. Win32 API işlevleri kullanarak, yürütme için ikincil iş parçacıkları da oluşturabilirsiniz. Bu iş parçacıkları MFC kitaplığını kullanabilir. Daha fazla bilgi için bkz. [Çoklu Iş parçacığı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Windows işletim sistemi için tüm programlar gibi, çerçeve uygulamanız `WinMain` işleve sahiptir. Ancak, bir çerçeve uygulamasında `WinMain`yazmayın. Sınıf kitaplığı tarafından sağlanır ve uygulama başlatıldığında çağrılır. `WinMain`, pencere sınıflarını kaydetme gibi standart Hizmetleri gerçekleştirir. Ardından uygulamayı başlatmak ve çalıştırmak için uygulama nesnesinin üye işlevlerini çağırır. (`WinMain` çağıran `CWinApp` üye işlevlerini geçersiz kılarak `WinMain` özelleştirebilirsiniz.)

Uygulamayı başlatmak için `WinMain` uygulama nesnenizin `InitApplication` ve `InitInstance` üye işlevlerini çağırır. Uygulamanın ileti döngüsünü çalıştırmak için, `WinMain` **Run** member işlevini çağırır. Sonlandırıldığında, `WinMain` uygulama nesnesinin `ExitInstance` üye işlevini çağırır.

> [!NOTE]
>  Bu belgede **kalın** olarak gösterilen adlar Microsoft Foundation Class Kitaplığı ve görsel C++tarafından sağlanan öğeleri gösterir. `monospaced` türünde gösterilen adlar, oluşturduğunuz veya geçersiz kıldığınız öğeleri gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CWinApp ve MFC Uygulama Sihirbazı](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[Geçersiz Kılınabilir CWinApp Üye İşlevleri](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)

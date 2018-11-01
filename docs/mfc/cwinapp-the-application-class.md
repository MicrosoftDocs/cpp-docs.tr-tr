---
title: 'CWinApp: Uygulama Sınıfı'
ms.date: 11/04/2016
f1_keywords:
- CWinApp
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
ms.openlocfilehash: a19d510dc4c8835497ff9e1bb7d5ca6242206fe9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551326"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Uygulama Sınıfı

MFC ana uygulama sınıfında başlatma, çalışan ve Windows işletim sistemi için bir uygulamanın sonlandırma kapsüller. Framework üzerine inşa edilmiş bir uygulama olmalıdır ve türetilen bir sınıfın yalnızca bir nesne [CWinApp](../mfc/reference/cwinapp-class.md). Bu nesne, Windows oluşturulmadan önce oluşturulur.

`CWinApp` türetilen `CWinThread`, yürütme veya daha fazla olabilir uygulamanız için ana iş parçacığı temsil eder. MFC, en son sürümlerinde `InitInstance`, **çalıştırma**, `ExitInstance`, ve `OnIdle` üye işlevleri olan gerçekten sınıfında `CWinThread`. Bu işlevler oldukları gibi burada açıklanan `CWinApp` üyeleri bunun yerine, nesnenin rol uygulama nesnesi yerine birincil iş parçacığı olarak tartışma işlemiyle ilgili olduğundan.

> [!NOTE]
>  Uygulama sınıfınızda, uygulamanızın yürütme birincil iş parçacığı oluşturur. Win32 API işlevleri'ni kullanarak, yürütme İkincil iş parçacıkları oluşturabilirsiniz. Bu iş parçacıkları MFC kitaplığını kullanabilirsiniz. Daha fazla bilgi için [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Windows işletim sistemi için tüm programı gibi framework uygulamanızı sahip bir `WinMain` işlevi. Bir framework uygulamasında, ancak sizin için yazma `WinMain`. Bu sınıf kitaplığı tarafından sağlanan ve uygulama başlatıldığında çağrılır. `WinMain` Pencere sınıflarını kaydetme gibi standart Hizmetleri gerçekleştirir. Daha sonra üye işlevleri uygulama nesnesi başlatmak ve uygulamayı çalıştırmak için çağırır. (Özelleştirebileceğiniz `WinMain` kılarak `CWinApp` üye işlevleri `WinMain` çağrıları.)

Uygulamayı başlatmak için `WinMain` uygulama nesnenizin çağırır `InitApplication` ve `InitInstance` üye işlevleri. Uygulamanın ileti döngüsü çalıştırmak için `WinMain` çağrıları **çalıştırma** üye işlevi. Sonlandırma üzerinde `WinMain` uygulama çağıran `ExitInstance` üye işlevi.

> [!NOTE]
>  Gösterilen adları **kalın** bu belgede Microsoft Foundation Class Kitaplığı ve Visual C++ tarafından sağlanan öğe belirtin. Gösterilen adları `monospaced` türü veya geçersiz kılamazsınız öğeleri gösterir.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[CWinApp ve MFC Uygulama Sihirbazı](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[Geçersiz Kılınabilir CWinApp Üye İşlevleri](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)


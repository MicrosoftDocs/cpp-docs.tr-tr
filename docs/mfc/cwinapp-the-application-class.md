---
description: 'Daha fazla bilgi edinin: CWinApp: uygulama sınıfı'
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
ms.openlocfilehash: 63979846ec5b4d5bb5452e98a3ac19474b4fcd0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301639"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Uygulama Sınıfı

MFC 'deki ana uygulama sınıfı, Windows işletim sistemi için bir uygulamanın başlatılmasını, çalıştırılmasını ve sonlandırılmasını kapsüller. Framework üzerinde oluşturulan bir uygulama, [CWinApp](reference/cwinapp-class.md)'dan türetilmiş bir sınıfın bir ve sadece bir nesnesine sahip olmalıdır. Bu nesne Windows oluşturulmadan önce oluşturulur.

`CWinApp` , `CWinThread` uygulamanız için yürütmenin ana iş parçacığını temsil eden, bir veya daha fazla iş parçacığı olabilen öğesinden türetilir. MFC 'nin son sürümlerinde, `InitInstance` , **Run**, `ExitInstance` ve `OnIdle` member işlevleri aslında sınıfınlardır `CWinThread` . Bu işlevler burada üye gibi tartışılmıştır `CWinApp` , çünkü tartışma nesnenin rolünü birincil iş parçacığı yerine uygulama nesnesi olarak ele alınmaktadır.

> [!NOTE]
> Uygulama sınıfınız, uygulamanızın yürütmenin birincil iş parçacığını oluşturur. Win32 API işlevleri kullanarak, yürütme için ikincil iş parçacıkları da oluşturabilirsiniz. Bu iş parçacıkları MFC kitaplığını kullanabilir. Daha fazla bilgi için bkz. [Çoklu Iş parçacığı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Windows işletim sistemi için tüm programlar gibi, çerçeve uygulamanız bir `WinMain` işleve sahiptir. Ancak, bir çerçeve uygulamasında yazmayın `WinMain` . Sınıf kitaplığı tarafından sağlanır ve uygulama başlatıldığında çağrılır. `WinMain` pencere sınıflarını kaydetme gibi standart Hizmetleri gerçekleştirir. Ardından uygulamayı başlatmak ve çalıştırmak için uygulama nesnesinin üye işlevlerini çağırır. ( `WinMain` Çağıran üye işlevlerini geçersiz kılarak özelleştirebilirsiniz `CWinApp` `WinMain` .)

Uygulamayı başlatmak için, `WinMain` uygulama nesnenizin `InitApplication` ve `InitInstance` üye işlevlerinizi çağırır. Uygulamanın ileti döngüsünü çalıştırmak için, `WinMain` **Run** member işlevini çağırır. Sonlandırıldığında, `WinMain` Uygulama nesnesinin `ExitInstance` üye işlevini çağırır.

> [!NOTE]
> Bu belgede **kalın** olarak gösterilen adlar Microsoft Foundation Class Kitaplığı ve Visual C++ tarafından sağlanan öğeleri gösterir. Tür ' de gösterilen adlar `monospaced` , oluşturduğunuz veya geçersiz kıldığınız öğeleri gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC konuları](general-mfc-topics.md)<br/>
[CWinApp ve MFC Uygulama Sihirbazı](cwinapp-and-the-mfc-application-wizard.md)<br/>
[Geçersiz kılınabilir CWinApp Üye Işlevleri](overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](special-cwinapp-services.md)

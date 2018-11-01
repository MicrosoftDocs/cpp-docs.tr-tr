---
title: Boşta Çevrim İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
ms.openlocfilehash: 1eff76e2e5fd98e63dccb9110882656f69da6539
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604297"
---
# <a name="idle-loop-processing"></a>Boşta Çevrim İşleme

Birçok uygulama gerçekleştirmek uzun işleme "arka planda." Bazen performansla ilgili önemli noktalar kullanarak bu iş için çoklu iş parçacığı kullanımı gerektirir. İş parçacığı içeren ek geliştirme ek yükü, MFC yapar boşta kalma süresi iş gibi basit görevler için önerilmeyen şekilde [ONIDLE](../mfc/reference/cwinthread-class.md#onidle) işlevi. Bu makalede, boşta işleme üzerinde odaklanır. Çoklu iş parçacığı bakın hakkında daha fazla bilgi için [çoklu iş parçacığı kullanımı konuları](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Bazı tür arka plan işlemesi sırasında kullanıcı aksi uygulamayla etkileşime aralıkları uygun şekilde gerçekleştirilir. Microsoft Windows işletim sistemi için geliştirilmiş bir uygulamada, uygulamanın boşta kalma süresi işleme uzun süren bir işlem içinde çok sayıda küçük parça bölerek gerçekleştirebilirsiniz. Her parça işledikten sonra uygulamayı kullanarak Windows için yürütme denetimi verir bir [PeekMessage](https://msdn.microsoft.com/library/windows/desktop/ms644943) döngü.

Bu makalede, iki boşta işleme uygulamanızdaki şekilde açıklanmaktadır:

- Kullanarak **PeekMessage** MFC'nin ana ileti döngüsü içinde.

- Başka bir gömme **PeekMessage** uygulamada başka bir yere döngü.

##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> MFC ileti döngüsündeki PeekMessage

MFC ile geliştirilmiş bir uygulamada, ana ileti döngüsü içinde `CWinThread` sınıfı içeren çağıran bir ileti döngüsü [PeekMessage](https://msdn.microsoft.com/library/windows/desktop/ms644943) Win32 API. Bu döngü ayrıca çağrıları `OnIdle` üye işlevinin `CWinThread` iletileri arasında. Bir uygulama iletileri bu boşta kalma süresi geçersiz kılarak işleyebilir `OnIdle` işlevi.

> [!NOTE]
>  `Run`, `OnIdle`, ve belirli bir üye işlevleri artık sınıf üyesi `CWinThread` yerine sınıfın `CWinApp`. `CWinApp` türetilen `CWinThread`.

Gerçekleştirme boşta işleme hakkında daha fazla bilgi için bkz. [ONIDLE](../mfc/reference/cwinthread-class.md#onidle) içinde *MFC başvurusu*.

##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage uygulamanızdaki başka bir yerde

Boş bir uygulamada işleme gerçekleştirmek için başka bir yöntemi, bir ileti döngüsü işlevlerinizi birinde eklemeye içerir. Bu ileti döngüsü bulunan MFC'nin ana ileti döngüsü için çok benzer [CWinThread::Run](../mfc/reference/cwinthread-class.md#run). MFC ile geliştirilen bir uygulamanın böyle bir döngüde ana ileti döngüsü aynı işlevlerin birçoğunu gerçekleştirmelidir anlamına gelir. Aşağıdaki kod parçası, MFC ile uyumlu bir ileti döngüsü yazma gösterir:

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

Katıştırılmış bir işlevde, bu kod, boşta işleme yapmak için var olduğu sürece döngüde kalır. Bu döngü içinde iç içe döngü tekrar tekrar çağırır `PeekMessage`. Bu çağrı, sıfır olmayan bir değer döndürür. sürece, döngü çağırır `CWinThread::PumpMessage` normal iletisini çeviri ve gönderme işlemleri için. Ancak `PumpMessage` belgelenmemiş, olduğundan, Visual C++ yüklemenizin \atlmfc\src\mfc dizinindeki ThrdCore.Cpp dosyasına kaynak kodunda inceleyebilirsiniz.

Bir kez ve iç döngü sona erdikten dış döngü için bir veya daha fazla çağrılarıyla boşta işleme gerçekleştirir `OnIdle`. İlk çağrı MFC'nin amaçları içindir. Ek çağrıları yapabileceğiniz `OnIdle` kendi arka plan işlerini gerçekleştirmek için.

Gerçekleştirme boşta işleme hakkında daha fazla bilgi için bkz. [ONIDLE](../mfc/reference/cwinthread-class.md#onidle) MFC Kitaplığı Başvurusu.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)


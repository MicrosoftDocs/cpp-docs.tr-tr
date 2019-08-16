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
ms.openlocfilehash: 72491c057f3bf7c531bb5515b07f1e9d0acf35d5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508408"
---
# <a name="idle-loop-processing"></a>Boşta Çevrim İşleme

Birçok uygulama arka planda uzun işlem yapar. " Bazen performans konuları söz konusu iş için çoklu iş parçacığı kullanımı için İş parçacıkları ek geliştirme yükü içerir, bu nedenle MFC 'nin [OnIdle](../mfc/reference/cwinthread-class.md#onidle) işlevinde kullandığı boşta kalma süresi gibi basit görevler için önerilmez. Bu makale, boşta işlemeye odaklanır. Çoklu iş parçacığı hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı konuları](../parallel/multithreading-support-for-older-code-visual-cpp.md)

Bazı arka plan işleme türleri, kullanıcının başka bir uygulamayla etkileşim kurmadığından aralıklar sırasında uygun şekilde yapılır. Microsoft Windows işletim sistemi için geliştirilmiş bir uygulamada, bir uygulama uzun bir işlemi birçok küçük parçaya bölerek boşta zaman işleme gerçekleştirebilir. Her parçayı işledikten sonra uygulama, [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) döngüsü kullanarak Windows 'a yürütme denetimi verir.

Bu makalede, uygulamanızda boşta işleme almanın iki yolu açıklanmaktadır:

- MFC 'nin ana ileti döngüsünde **PeekMessage** kullanma.

- Başka bir **PeekMessage** döngüsünü uygulamada başka bir yere ekleme.

##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC Ileti döngüsünde PeekMessage

MFC ile geliştirilen bir uygulamada, `CWinThread` sınıftaki ana ileti döngüsü, [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) Win32 API çağıran bir ileti döngüsü içerir. Bu döngü Ayrıca iletiler `OnIdle` `CWinThread` arasındaki üye işlevini çağırır. Bir uygulama, `OnIdle` işlevi geçersiz kılarak bu boşta zaman içindeki iletileri işleyebilir.

> [!NOTE]
>  `Run`, `OnIdle`ve bazı diğer üye işlevleri, sınıfı `CWinApp`yerine artık sınıfın `CWinThread` üyeleridir. `CWinApp`, öğesinden `CWinThread`türetilir.

Boşta işleme gerçekleştirme hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [OnIdle](../mfc/reference/cwinthread-class.md#onidle) .

##  <a name="_core_peekmessage_elsewhere_in_your_application"></a>PeekMessage, uygulamanızda başka bir yerde

Bir uygulamada boş işlem gerçekleştirmeye yönelik başka bir yöntem, işlevlerinizin birine bir ileti döngüsü katıştırmayı içerir. Bu ileti döngüsü,,, şunu, bir,,,,,, [](../mfc/reference/cwinthread-class.md#run), şunu,,,,,,, Bu, MFC ile geliştirilen bir uygulama içindeki bir döngünün, ana ileti döngüsüyle aynı işlevlerin birçoğunu gerçekleştirmesi gerekir. Aşağıdaki kod parçası, MFC ile uyumlu bir ileti döngüsünün yazılmasını göstermektedir:

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

Bu kod, bir işleve eklenmiş olan bu kod, işlem için boşta işleme olduğu sürece döngü sağlar. Bu döngü içinde, iç içe geçmiş bir döngü `PeekMessage`tekrar tekrar çağırır. Bu çağrı sıfır dışında bir değer döndürdüğü sürece döngü, normal ileti çevirisi `CWinThread::PumpMessage` ve gönderme işlemleri için çağırır. Açıklanmasa `PumpMessage` da, kaynak kodunu Visual C++ yüklemenizin \atlmfc\src\mfc dizinindeki ThrdCore. cpp dosyasında inceleyebilirsiniz.

İç döngü sona erdikten sonra, dış döngü bir veya daha fazla çağrısı `OnIdle`olan boşta işleme gerçekleştirir. İlk çağrı MFC 'nin amaçlarına yöneliktir. Kendi arka plan işinizi yapmak `OnIdle` için ek çağrılar yapabilirsiniz.

Boşta işleme gerçekleştirme hakkında daha fazla bilgi için bkz. MFC Kitaplığı başvurusunda [OnIdle](../mfc/reference/cwinthread-class.md#onidle) .

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)

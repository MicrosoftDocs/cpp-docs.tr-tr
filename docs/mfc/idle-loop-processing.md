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
ms.openlocfilehash: 9579d4bb8768b0227453af401d6fdc8a8bd482b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376007"
---
# <a name="idle-loop-processing"></a>Boşta Çevrim İşleme

Birçok uygulama "arka planda" uzun işleme gerçekleştirir. Bazen performans hususları, bu tür işler için çok iş parçacığı kullanmayı belirler. İş parçacıkları ek geliştirme yükü içerir, bu nedenle MFC'nin [OnIdle](../mfc/reference/cwinthread-class.md#onidle) işlevinde yaptığı boşta zaman çalışması gibi basit görevler için önerilmez. Bu makalede, boşta işleme üzerinde duruluyor. Çok iş parçacığı hakkında daha fazla bilgi için, [Multithreading Konular](../parallel/multithreading-support-for-older-code-visual-cpp.md)bakın.

Bazı arka plan işleme, kullanıcının uygulamayla başka bir şekilde etkileşimde olmadığı aralıklarla uygun şekilde yapılır. Microsoft Windows işletim sistemi için geliştirilen bir uygulamada, bir uygulama uzun bir işlemi birçok küçük parçaya bölerek boşta zaman işleme gerçekleştirebilir. Her parçayı işledikten sonra, uygulama bir [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) döngüsü kullanarak Windows'a yürütme denetimi verir.

Bu makalede, uygulamanızda boşta işleme yapmak için iki yol açıklanmaktadır:

- MFC'nin ana ileti döngüsünde **PeekMessage'ı** kullanma.

- Uygulamada başka bir yere başka bir **PeekMessage** döngüsü katıştırma.

## <a name="peekmessage-in-the-mfc-message-loop"></a><a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC İleti Döngüsünde PeekMessage

MFC ile geliştirilen bir uygulamada, sınıftaki `CWinThread` ana ileti döngüsü [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) Win32 API çağıran bir ileti döngüsü içerir. Bu döngü, `OnIdle` iletiler `CWinThread` arasındaki üye işlevini de çağırır. Bir uygulama `OnIdle` işlevi geçersiz kılarak bu boşta zamanda iletileri işleyebilir.

> [!NOTE]
> `Run`, `OnIdle`ve bazı diğer üye işlevler `CWinThread` artık sınıf `CWinApp`yerine sınıfın üyeleridir. `CWinApp``CWinThread`türetilmiştir.

Boşta işleme hakkında daha fazla bilgi için *MFC Başvurusu'nda* [OnIdle'a](../mfc/reference/cwinthread-class.md#onidle) bakın.

## <a name="peekmessage-elsewhere-in-your-application"></a><a name="_core_peekmessage_elsewhere_in_your_application"></a>PeekMessage Uygulamanızın Başka Yerinde

Bir uygulamada boşta işleme gerçekleştirmek için başka bir yöntem işlevlerinizden birine bir ileti döngüsü gömme içerir. Bu ileti döngüsü CWinThread bulunan MFC ana ileti döngüsü, çok [benzer::Çalıştır](../mfc/reference/cwinthread-class.md#run). Bu, MFC ile geliştirilen bir uygulamada böyle bir döngü ana ileti döngüsü olarak aynı işlevleri birçok gerçekleştirmek gerektiği anlamına gelir. Aşağıdaki kod parçası, MFC ile uyumlu bir ileti döngüsü yazmayı gösterir:

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

Bir işleve katıştırılmış olan bu kod, boşta işleme olduğu sürece döngüler. Bu döngü içinde, iç içe `PeekMessage`geçen bir döngü art arda çağırır. Bu arama sıfır olmayan bir değer döndürderken, döngü normal ileti çevirisi ve gönderme gerçekleştirmeyi çağırır. `CWinThread::PumpMessage` Belgelenmemiş olmasına rağmen, `PumpMessage` Visual C++ yüklemenizin \atlmfc\src\mfc dizinindeki ThrdCore.Cpp dosyasındaki kaynak kodunu inceleyebilirsiniz.

İç döngü sona erdiğinde, dış döngü bir veya daha `OnIdle`fazla çağrı ile boşta işleme gerçekleştirir. İlk arama MFC'nin amaçları içindir. Kendi arka plan `OnIdle` çalışmanızı yapmak için ek aramalar yapabilirsiniz.

Boşta işleme hakkında daha fazla bilgi için MFC Kitaplık Başvurusu'nda [OnIdle'a](../mfc/reference/cwinthread-class.md#onidle) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)

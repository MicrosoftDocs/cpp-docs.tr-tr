---
title: "Boşta çevrim işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: baabba60ffaf886b7a34acfbff5b923a4495fa1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idle-loop-processing"></a>Boşta Çevrim İşleme
Birçok uygulama "arka planda." uzun yönlendirilmeden Bazen performans değerlendirmeleri gibi iş için çoklu iş parçacığı kullanımı kullanarak dikte. İş parçacığı içeren ek geliştirme yükünü MFC yapar boşta kalma süresi iş gibi basit görevleri için önerilmez şekilde [ONIDLE](../mfc/reference/cwinthread-class.md#onidle) işlevi. Bu makalede üzerindeki boşta işleme odaklanır. Çoklu iş parçacığı kullanımı, bkz: hakkında daha fazla bilgi için [çoklu iş parçacığı kullanımı konuları](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Arka plan işlemesi bazı tür kullanıcı Aksi durumda uygulama ile etkileşim değil aralıklar süresince uygun şekilde yapılır. Microsoft Windows işletim sistemi için geliştirilen bir uygulamada, çok sayıda küçük parça uzun süren bir işlem bölerek boşta kalma süresi işleme uygulama gerçekleştirebilirsiniz. Her parça işledikten sonra uygulamayı Windows kullanmanın yürütme denetimi verir bir [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) döngü.  
  
 Bu makalede, uygulamanızda işleme boşta iki yolu açıklanmaktadır:  
  
-   Kullanarak **PeekMessage** MFC'nin ana ileti Döngüdeki.  
  
-   Başka katıştırma **PeekMessage** uygulamada başka bir yere döngü.  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC ileti döngüsü PeekMessage  
 MFC ile geliştirilen bir uygulamada ana ileti döngü içinde `CWinThread` sınıfı içeren çağıran bir ileti döngüsü [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Win32 API. Bu döngü ayrıca çağrıları `OnIdle` üye işlevini `CWinThread` iletileri arasında. Bir uygulama iletileri bu boşta kalma süresi geçersiz kılarak işleyebilir `OnIdle` işlevi.  
  
> [!NOTE]
>  **Çalıştırma**, `OnIdle`, ve belirli bir üye işlevleri şimdi sınıf üyesi `CWinThread` yerine sınıfının `CWinApp`. `CWinApp`türetilmiş `CWinThread`.  
  
 Boşta işleme gerçekleştirme hakkında daha fazla bilgi için bkz: [ONIDLE](../mfc/reference/cwinthread-class.md#onidle) içinde *MFC başvurusu*.  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a>PeekMessage uygulamanızda başka bir yerde  
 Bir ileti döngüsü işlevlerinizi birinde katıştırma bir uygulamada işleme boşta gerçekleştirmek için başka bir yöntem içerir. Bu ileti döngüsü bulunan MFC'nin ana ileti döngüsüne çok benzer [CWinThread::Run](../mfc/reference/cwinthread-class.md#run). MFC ile geliştirilen bir uygulamayı bu tür bir döngüde ana ileti döngüsü aynı işlevleri çoğunu gerçekleştirmeniz gerekir anlamına gelir. Aşağıdaki kod parçası, MFC ile uyumlu bir ileti döngüsü yazma gösterir:  
  
 [!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]  
  
 Yapmak için boşta işleme var olduğu sürece bir işlevde katıştırılmış bu kodu döngüye girer. Bu döngü içinde iç içe geçmiş bir döngü art arda çağırır **PeekMessage**. Bu çağrı, sıfır olmayan bir değer döndürür sürece, döngü çağırır `CWinThread::PumpMessage` normal ileti çeviri ve göndermeyi gerçekleştirmek için. Ancak `PumpMessage` belgelenmemiş, olduğundan, kaynak kodu Visual C++ yüklemenizin \atlmfc\src\mfc dizindeki ThrdCore.Cpp dosyasında inceleyebilirsiniz.  
  
 Bir kez iç döngü sona erer dış döngü için bir veya daha fazla çağrılarla boşta işleme gerçekleştirir `OnIdle`. İlk çağrıda MFC'nin amacıyla kullanılır. Ek çağrı yapmak `OnIdle` arka plan iş yapmak için.  
  
 Boşta işleme gerçekleştirme hakkında daha fazla bilgi için bkz: [ONIDLE](../mfc/reference/cwinthread-class.md#onidle) MFC Kitaplığı Başvurusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC Konuları](../mfc/general-mfc-topics.md)


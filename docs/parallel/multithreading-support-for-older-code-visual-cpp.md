---
title: "Eski kod (Visual C++) için çoklu iş parçacığı desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d949c1ff19be6f3b89673753fdaccc2996bbef36
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)
Visual C++ yürütme eşzamanlı çalışan birden çok eşzamanlı iş parçacığına sahip olmanızı sağlar. İle çoklu iş parçacığı kullanımı, arkaplan görevleri, eşzamanlı girdi akışları ile yönetme, bir kullanıcı arabirimi ve daha fazlasını yapabilirsiniz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [C ve Win32 ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-c-and-win32.md)  
 Microsoft Windows ile çoklu iş parçacığı kullanan uygulamalar oluşturmak için destek sağlar  
  
 [C++ ve MCF ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)  
 İşlemler ve iş parçacıkları nedir ve ne MFC yaklaşımının açıklar çoklu iş parçacığı kullanımı değil.  
  
 [Çoklu iş parçacığı kullanımı ve yerel ayarlar](../parallel/multithreading-and-locales.md)  
 C çalışma zamanı kitaplığı ve birden çok iş parçacıklı uygulamada C++ Standart Kitaplığı yerel ayar işlevselliğini kullanırken çıkabilecek sorunlar açıklanır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 Bir uygulama içinde yürütme iş parçacığı temsil eder.  
  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Win32 eşitleme nesneleri için ortak işlevselliği sağlayan saf sanal bir sınıfı tanımlar.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Bir kaynağa erişmek için bir veya daha fazla işlemde sınırlı sayıda iş parçacığına izin veren bir eşitleme nesnesi olan bir semafor temsil eder.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Bir iş parçacığı birbirini dışlayan bir kaynağa erişim izni veren bir eşitleme nesnesi olan bir mutex temsil eder.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Bir kaynak veya kod bölümüne erişmek için aynı anda tek bir iş parçacığı veren bir eşitleme nesnesi olan önemli bir bölümünü temsil eder.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Başka bir olayın oluştuğunu bildirmek bir iş parçacığı veren bir eşitleme nesnesi olan bir olayı temsil eder.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Birden çok iş parçacıklı programda kaynaklara erişimi denetlemek kullanılan erişim denetim mekanizmasını temsil eder.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 Birden çok iş parçacıklı programda bir kaynağa erişimi denetlemek kullanılan erişim denetim mekanizmasını temsil eder.  
  
 [(NOTINBUILD) Visual C++ programlama yöntemleri](http://msdn.microsoft.com/en-us/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Visual C++ kitaplıkları hakkındaki kavramsal bilgileri ve çeşitli kodlama teknolojilerini ve tekniklerini açıklayan konuların bağlantılarını sağlar.
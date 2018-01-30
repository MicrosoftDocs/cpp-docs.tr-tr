---
title: "Eski kod (Visual C++) için çoklu iş parçacığı desteği | Microsoft Docs"
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
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e082fd9c3f4c34c97f461a11dcec14d778affd8
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)
Visual C++ yürütme eşzamanlı çalışan birden çok eşzamanlı iş parçacığına sahip olmanızı sağlar. İle çoklu iş parçacığı kullanımı, arkaplan görevleri, eşzamanlı girdi akışları ile yönetme, bir kullanıcı arabirimi ve daha fazlasını yapabilirsiniz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)  
 Microsoft Windows ile çoklu iş parçacığı kullanan uygulamalar oluşturmak için destek sağlar  
  
 [C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)  
 İşlemler ve iş parçacıkları nedir ve ne MFC yaklaşımının açıklar çoklu iş parçacığı kullanımı değil.  
  
 [Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar](../parallel/multithreading-and-locales.md)  
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

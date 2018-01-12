---
title: "C ve Win32 ile çoklu iş parçacığı kullanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30c7833a4df80669b6223f1fe6b1ccceed0257cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-with-c-and-win32"></a>C ve Win32 ile Çoklu İş Parçacığı Kullanımı
Microsoft Visual C++, Microsoft Windows ile çoklu iş parçacığı kullanan uygulamalar oluşturmak için destek sağlar: Windows XP, Windows 2000, Windows NT, Windows Me ve Windows 98. Eşzamanlı klavye ve fare girdisi gibi birden çok etkinlikleri yönetmek uygulamanız gerekiyorsa birden çok iş parçacığı kullanmayı düşünmelisiniz. İkinci bir iş parçacığı fare etkinliklerini filtreler sırada bir iş parçacığı klavye girişini işleyebilir. Üçüncü bir iş parçacığı, fare ve klavye iş parçacığı dayalı ekran güncelleştirebilirsiniz. Aynı anda başka bir iş parçacığı disk dosyalarına erişebilir veya veri iletişim bağlantı noktasından alabilir.  
  
 Visual C++ ile birden çok iş parçacığı ile programa iki yolu vardır: Microsoft Foundation Class (MFC) kitaplığı veya C çalışma zamanı kitaplığı ve Win32 API kullanın. MFC ile çoklu iş parçacığı kullanan uygulamalar oluşturma hakkında daha fazla bilgi için bkz: [C++ ve MCF ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-cpp-and-mfc.md) C'deki ilgili aşağıdaki konuları okuma sonra  
  
 Bu konular, çoklu iş parçacığı programları oluşturmayı destekleyen Visual C++ özellikleri açıklar.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Ne çoklu iş parçacığı kullanımı hakkında](../parallel/multithread-programs.md)  
  
-   [Kitaplık desteği için çoklu iş parçacığı kullanımı](../parallel/library-support-for-multithreading.md)  
  
-   [Dosyaları dahil çoklu iş parçacığı kullanımı](../parallel/include-files-for-multithreading.md)  
  
-   [İş parçacığı denetimi için C çalışma zamanı kitaplık işlevleri](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Örnek çoklu iş parçacığı kullanan C programı](../parallel/sample-multithread-c-program.md)  
  
-   [Çoklu iş parçacığı kullanan Win32 programı yazma](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [Çoklu iş parçacığı kullanan programları derleme ve bağlama](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Çoklu iş parçacığı kullanan programlarda sorun alanlarından kaçınma](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [İş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)
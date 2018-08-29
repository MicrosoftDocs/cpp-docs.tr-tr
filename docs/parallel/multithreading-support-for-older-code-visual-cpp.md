---
title: Eski kod (Visual C++) için çoklu iş parçacığı desteği | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b1b301186036460acc07a526267503da8b97678
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132108"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)
Visual C++ birden çok eşzamanlı iş parçacığı aynı anda çalışan yürütme sahip olmanızı sağlar. İle çoklu iş parçacığı, arka plan görevleri, eşzamanlı giriş akışları yönetme, bir kullanıcı arabirimi ve daha fazlasını yönetin.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 
[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)  
Microsoft Windows ile çoklu iş parçacığı kullanan uygulamalar oluşturmak için destek sağlar.  
  
[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)  
İşlemler ve iş parçacıklarının ne olduğunu ve MFC yaklaşımının ne açıklar çoklu iş parçacığı kullanımı olan.  
  
[Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar](multithreading-and-locales.md)  
Hem C çalışma zamanı kitaplığı, hem de C++ Standart Kitaplığı çok iş parçacıklı bir uygulamada bulunan yerel ayar işlevselliği kullanıldığında ortaya çıkan sorunları açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 
[CWinThread](../mfc/reference/cwinthread-class.md)  
Uygulamadaki bir iş parçacığını temsil eder.  
  
[CSyncObject](../mfc/reference/csyncobject-class.md)  
Win32'de eşitleme nesneleriyle ortak işlevselliği sağlayan saf sanal sınıfı açıklar.  
  
[CSemaphore](../mfc/reference/csemaphore-class.md)  
Bir kaynağa erişmek için bir veya daha fazla işlemde sınırlı sayıda iş parçacığına izin veren bir eşitleme nesnesi olan bir semaforu temsil eder.  
  
[CMutex](../mfc/reference/cmutex-class.md)  
Bir iş parçacığı bir kaynağa karşılıklı olarak dışlama erişimine izin veren bir eşitleme nesnesi olan mutex'i temsil eder.  
  
[CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
Bir kaynağa veya kod bölümüne erişmek için bir seferde bir iş parçacığına izin veren bir eşitleme nesnesi olan kritik bölümü temsil eder.  
  
[CEvent](../mfc/reference/cevent-class.md)  
Başka bir olayın oluştuğunu bildirmek bir iş parçacığına izin veren bir eşitleme nesnesi olan bir olayı temsil eder.  
  
[CMultiLock](../mfc/reference/cmultilock-class.md)  
Çoklu iş parçacığı kullanan programda kaynaklara erişimi denetlemek için kullanılan erişim denetim mekanizmasını temsil eder.  
  
[CSingleLock](../mfc/reference/csinglelock-class.md)  
Çoklu iş parçacığı kullanan programda bir kaynağa erişimi denetlemek için kullanılan erişim denetim mekanizmasını temsil eder.  
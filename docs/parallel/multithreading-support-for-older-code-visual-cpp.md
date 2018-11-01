---
title: Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)
ms.date: 08/27/2018
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
ms.openlocfilehash: 649e26c3f0704dfd6740b1a250613545e29316a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457739"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)

Visual C++ birden çok eşzamanlı iş parçacığı aynı anda çalışan yürütme sahip olmanızı sağlar. İle çoklu iş parçacığı, arka plan görevleri, eşzamanlı giriş akışları yönetme, bir kullanıcı arabirimi ve daha fazlasını yönetin.

## <a name="in-this-section"></a>Bu Bölümde

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)<br/>
Microsoft Windows ile çoklu iş parçacığı kullanan uygulamalar oluşturmak için destek sağlar.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)<br/>
İşlemler ve iş parçacıklarının ne olduğunu ve MFC yaklaşımının ne açıklar çoklu iş parçacığı kullanımı olan.

[Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar](multithreading-and-locales.md)<br/>
Hem C çalışma zamanı kitaplığı, hem de C++ Standart Kitaplığı çok iş parçacıklı bir uygulamada bulunan yerel ayar işlevselliği kullanıldığında ortaya çıkan sorunları açıklar.

## <a name="related-sections"></a>İlgili Bölümler

[CWinThread](../mfc/reference/cwinthread-class.md)<br/>
Uygulamadaki bir iş parçacığını temsil eder.

[CSyncObject](../mfc/reference/csyncobject-class.md)<br/>
Win32'de eşitleme nesneleriyle ortak işlevselliği sağlayan saf sanal sınıfı açıklar.

[CSemaphore](../mfc/reference/csemaphore-class.md)<br/>
Bir kaynağa erişmek için bir veya daha fazla işlemde sınırlı sayıda iş parçacığına izin veren bir eşitleme nesnesi olan bir semaforu temsil eder.

[CMutex](../mfc/reference/cmutex-class.md)<br/>
Bir iş parçacığı bir kaynağa karşılıklı olarak dışlama erişimine izin veren bir eşitleme nesnesi olan mutex'i temsil eder.

[CCriticalSection](../mfc/reference/ccriticalsection-class.md)<br/>
Bir kaynağa veya kod bölümüne erişmek için bir seferde bir iş parçacığına izin veren bir eşitleme nesnesi olan kritik bölümü temsil eder.

[CEvent](../mfc/reference/cevent-class.md)<br/>
Başka bir olayın oluştuğunu bildirmek bir iş parçacığına izin veren bir eşitleme nesnesi olan bir olayı temsil eder.

[CMultiLock](../mfc/reference/cmultilock-class.md)<br/>
Çoklu iş parçacığı kullanan programda kaynaklara erişimi denetlemek için kullanılan erişim denetim mekanizmasını temsil eder.

[CSingleLock](../mfc/reference/csinglelock-class.md)<br/>
Çoklu iş parçacığı kullanan programda bir kaynağa erişimi denetlemek için kullanılan erişim denetim mekanizmasını temsil eder.
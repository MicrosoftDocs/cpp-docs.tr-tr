---
title: "Uzantı DLL'leri: Genel Bakış"
ms.date: 11/04/2016
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: 1967370f587b0b78c4e68ebff14804b20f158bd0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498208"
---
# <a name="mfc-extension-dlls-overview"></a>MFC uzantı DLL'leri: genel bakış

Bir MFC uzantılı DLL genellikle varolan Microsoft Foundation Class Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan bir DLL'dir. MFC uzantı DLL'leri MFC (diğer adıyla MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturuldu. Bir MFC uzantılı DLL, MFC paylaşılan sürümü ile oluşturulmuş yalnızca MFC yürütülebilir dosyaları (uygulama veya Normal MFC DLL'leri) kullanabilirsiniz. Bir MFC uzantılı DLL ile yeni özel sınıflar türetebilir ve ardından MFC genişletilmiş bu sürümü DLL'nizi çağıran uygulamalara sunar.

Uzantı DLL'leri, uygulama ve DLL arasında MFC'den türetilmiş nesneler geçirmek için de kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri, nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün bir şekilde paylaşılan MFC DLL sürümünü kullanırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ile MFC uzantısı DLL'leri arasında MFC'den türetilmiş nesne işaretçileri.

MFC örnek bir MFC uzantılı DLL temel gereksinimlerini karşılayan bir DLL örneği için bkz. [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). Özellikle, Testdll1.cpp ve Testdll2.cpp dosyalarına bakın.

AFXDLL terimi artık Visual C++ belgelerinde kullanılan unutmayın. Bir MFC uzantılı DLL eski AFXDLL aynı özelliklere sahiptir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir MFC uzantılı DLL başlatma](../build/run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC uzantısı DLL’leri](../build/extension-dlls.md)

- [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC Dışı DLL'ler: Genel Bakış](../build/non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL Türleri](../build/kinds-of-dlls.md)
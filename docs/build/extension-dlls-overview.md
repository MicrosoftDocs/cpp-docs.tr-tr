---
title: "Uzantı DLL'leri: Genel Bakış"
ms.date: 05/06/2019
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: ea8e950e28907ea1a4a85c1f39392d5505f08c49
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221364"
---
# <a name="mfc-extension-dlls-overview"></a>MFC uzantı DLL'leri: Genel Bakış

Bir MFC uzantılı DLL genellikle varolan Microsoft Foundation Class Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan bir DLL'dir. MFC uzantı DLL'leri MFC (diğer adıyla MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturuldu. Bir MFC uzantılı DLL, MFC paylaşılan sürümü ile oluşturulmuş yalnızca MFC yürütülebilir dosyaları (uygulama veya Normal MFC DLL'leri) kullanabilirsiniz. Bir MFC uzantılı DLL ile yeni özel sınıflar türetebilir ve ardından MFC genişletilmiş bu sürümü DLL'nizi çağıran uygulamalara sunar.

Uzantı DLL'leri, uygulama ve DLL arasında MFC'den türetilmiş nesneler geçirmek için de kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri, nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün bir şekilde paylaşılan MFC DLL sürümünü kullanırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ile MFC uzantısı DLL'leri arasında MFC'den türetilmiş nesne işaretçileri.

MFC örnek bir MFC uzantılı DLL temel gereksinimlerini karşılayan bir DLL örneği için bkz. [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). Özellikle, Testdll1.cpp ve Testdll2.cpp dosyalarına bakın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir MFC uzantılı DLL başlatma](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC uzantısı DLL’leri](extension-dlls.md)

- [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL Türleri](kinds-of-dlls.md)

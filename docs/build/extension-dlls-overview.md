---
description: "Daha fazla bilgi edinin: MFC uzantı dll 'Leri: genel bakış"
title: "Uzantı DLL'leri: Genel Bakış"
ms.date: 05/06/2019
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: b877eeaae2e67466d4b695820659c5718d552d0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162930"
---
# <a name="mfc-extension-dlls-overview"></a>MFC uzantısı DLL’leri: Genel Bakış

MFC uzantı DLL 'si, genellikle varolan Microsoft Foundation Class Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan bir DLL 'dir. MFC uzantı dll 'Leri MFC 'nin dinamik bağlantı kitaplığı sürümü (MFC 'nin paylaşılan sürümü olarak da bilinir) kullanılarak oluşturulmuştur. MFC 'nin paylaşılan sürümüyle oluşturulmuş yalnızca MFC yürütülebilir dosyaları (uygulamalar veya normal MFC DLL 'Leri) MFC uzantısı DLL kullanabilir. MFC uzantısı DLL 'SI ile MFC 'den yeni özel sınıflar türetebilir ve ardından bu genişletilmiş sürümü MFC 'nin DLL 'nizi çağıran uygulamalara sunabilirsiniz.

Uzantı dll 'Leri, uygulama ve DLL arasında MFC 'den türetilmiş nesneleri geçirmek için de kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri, nesnenin oluşturulduğu modülde bulunur. Bu işlevler, MFC 'nin paylaşılan DLL sürümü kullanılırken düzgün bir şekilde aktarıldığından, bir uygulama ile yüklenen MFC uzantı dll 'Leri arasında MFC veya MFC 'den türetilmiş nesne işaretçilerini serbestçe geçirebilirsiniz.

MFC uzantısı DLL 'inin temel gereksinimlerini karşılayan bir DLL örneği için, bkz. MFC örnek [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). Özellikle, TESTDLL1. cpp ve TESTDLL2. cpp dosyalarına bakın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [MFC uzantı DLL 'sini başlatma](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC uzantısı DLL’leri](extension-dlls.md)

- [Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL Türleri](kinds-of-dlls.md)

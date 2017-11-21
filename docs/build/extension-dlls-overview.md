---
title: "Uzantı DLL'leri: Genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39ed1531be553a66f22ac8b93e898a91cf5006e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-extension-dlls-overview"></a>MFC uzantı DLL'leri: genel bakış
MFC uzantı DLL'si genellikle mevcut Microsoft Foundation Class Kitaplığı sınıflarından türetilmiş yeniden kullanılabilir sınıfları uygulayan bir DLL'dir. MFC uzantı DLL'leri MFC'nin (olarak da bilinen MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturulur. MFC uzantı DLL'si MFC paylaşılan sürümü ile oluşturulan yalnızca MFC yürütülebilir dosyaları (uygulamalar veya Normal MFC DLL'leri) kullanabilirsiniz. MFC DLL uzantısı ile yeni özel sınıflar türetebilir ve ardından bu genişletilmiş sürümüne MFC DLL çağıran uygulamalar sunar.  
  
 Uzantı DLL'leri de uygulama ve DLL arasında MFC'den türetilen nesneleri geçirmek için kullanılabilir. Geçirilen nesneyle ilişkili üye işlevleri nesne oluşturulduğu modülünde mevcut. Bu işlevler düzgün paylaşılan MFC'nin DLL sürümü kullanılırken dışarı aktarıldığı için MFC serbestçe geçirebilir veya uygulama ve MFC uzantı DLL'leri arasında MFC türetilmiş nesne işaretçileri.  
  
 MFC uzantı DLL'si temel gereksinimlerini karşılayan bir DLL örneği için bkz: MFC örnek [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). Özellikle, Testdll1.cpp ve Testdll2.cpp dosyalarına bakın.  
  
 AFXDLL teriminin artık Visual C++ belgelerde kullanılan unutmayın. MFC uzantı DLL'si eski AFXDLL aynı özelliklere sahip.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [MFC uzantı DLL başlatma](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [MFC uzantı DLL'leri](../build/extension-dlls.md)  
  
-   [Normal MFC DLL'lerde veritabanı, OLE ve yuva MFC uzantı DLL'leri kullanma](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC dışı DLL'ler: genel bakış](../build/non-mfc-dlls-overview.md)  
  
-   [Statik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL türleri](../build/kinds-of-dlls.md)
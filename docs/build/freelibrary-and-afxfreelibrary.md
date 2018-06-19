---
title: FreeLibrary ve AfxFreeLibrary | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs:
- C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1e1bf5f1a05438ddf89af86c9b0d12e7885b901
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367517"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary ve AfxFreeLibrary
Açıkça DLL çağrı bağlantı işlemleri [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) işlev DLL modülü artık gerekli olmadığında. Bu modülün başvuru sayısını azaltır işlev ve başvuru sayısı sıfır olursa, işlemin adres alanından eşlemesini.  
  
 Bir MFC uygulamasında kullanmak [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) yerine `FreeLibrary` MFC uzantı DLL kaldırmak için. Arabirim (işlev prototipi) için `AfxFreeLibrary` aynı `FreeLibrary`.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Bir DLL'e örtük olarak bağlanma](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [LoadLibrary ve AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
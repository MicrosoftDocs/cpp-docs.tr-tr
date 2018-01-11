---
title: LoadLibrary ve AfxLoadLibrary | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LoadLibrary
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03fc696af7605f9937ecddf40a06a0c020aff82c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary ve AfxLoadLibrary
İşler çağrısı [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) (veya [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) açıkça bir DLL'e bağlanmak için. İşlev başarılı olursa, belirtilen DLL çağırma işlemi adres alanına eşler ve diğer işlevleri açıkça bağlamada ile kullanılan DLL için bir işleyici döner — Örneğin, `GetProcAddress` ve `FreeLibrary`.  
  
 `LoadLibrary`örtük olarak bağlama için kullanılanla aynı arama sırasını kullanarak DLL bulmaya çalışır. Sistem DLL'yi bulamazsa veya giriş noktası işlevi FALSE döndürürse `LoadLibrary` NULL döndürür. Varsa çağrısı `LoadLibrary` arama işlemi adres alanına zaten eşleştirilmiş bir DLL modülü belirtir işlevi bir tanıtıcı artırır ve DLL modülü başvurusu sayısını döndürür.  
  
 DLL bir giriş noktası işlevi varsa işletim sistemi çağıran iş parçacığının bağlamında işlevi çağırır `LoadLibrary`. DLL, önceki çağrısı nedeniyle işleme zaten bağlıysa, giriş noktası işlevi çağrılmaz `LoadLibrary` karşılık gelen hiçbir çağrısına sahip `FreeLibrary` işlevi.  
  
 MFC uzantı DLL'leri yükleme MFC uygulamaları için kullanmanızı öneririz `AfxLoadLibrary` yerine `LoadLibrary`. `AfxLoadLibrary`işler iş parçacığı eşitleme çağırmadan önce `LoadLibrary`. (İşlev prototipi) arabirimine `AfxLoadLibrary` aynı `LoadLibrary`.  
  
 Windows DLL yüklenemiyorsa, işlem hatadan kurtarmak deneyebilirsiniz. Örneğin, işlem hata kullanıcıya bildirmek ve dll Dosyasının başka bir yolu belirtmesini isteyin.  
  
> [!IMPORTANT]
>  Windows NT 4, Windows 2000 veya Windows XP (SP1) öncesinde altında çalışacak şekilde kodu ise DLL'lerin tam yolunu belirttiğinizden emin olun. Dosyalar yüklendiğinde bu işletim sistemlerinde, geçerli dizin ilk aranır. Dosya yolunu uygun değil, hedeflenen değil bir dosyası yüklenmiş.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Bir DLL'e örtük olarak bağlanma](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [DLL bulmak için Windows tarafından kullanılan arama yolu](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [FreeLibrary ve AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)
---
title: DLL bulmak için Windows tarafından kullanılan yolu arama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 166b5fccf6dd231029f79fede837909a49e7fc4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="search-path-used-by-windows-to-locate-a-dll"></a>DLL Bulmak için Windows Tarafından Kullanılan Arama Yolu
Örtük ve açık bağlama ile Windows önce "bilinen DLL'ler" Kernel32.dll ve User32.dll gibi arar. Windows sonra DLL'leri aşağıdaki sırayla arar:  
  
1.  Geçerli işlem için yürütülebilir modülün bulunduğu dizini.  
  
2.  Geçerli dizin.  
  
3.  Windows Sistem dizini. **GetSystemDirectory** işlevi bu dizinin yolunu alır.  
  
4.  Windows dizinidir. **GetWindowsDirectory** işlevi bu dizinin yolunu alır.  
  
5.  PATH ortam değişkeninde listelenen dizinler.  
  
    > [!NOTE]
    >  LIBPATH ortam değişkeni kullanılmaz.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Bir DLL'e örtük olarak bağlanma](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Bir DLL'e açıkça bağlanma](../build/linking-an-executable-to-a-dll.md#linking-explicitly)  
  
-   [Hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)
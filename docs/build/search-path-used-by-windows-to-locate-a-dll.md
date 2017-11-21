---
title: "DLL bulmak için Windows tarafından kullanılan yolu arama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 79f6ca137c16100ac1d6b9bfa818f35d5ae21f14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)
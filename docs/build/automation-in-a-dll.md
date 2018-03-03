---
title: DLL'de Otomasyon | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e3630aab764988ad86e6120301dfff548ad4368
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="automation-in-a-dll"></a>DLL'de Otomasyon
MFC DLL Sihirbazı'nda Otomasyon seçeneğini seçtiğinizde, sihirbaz, aşağıdaki sağlar:  
  
-   Başlatıcı nesne Açıklama Dili (. ODL) dosyası  
  
-   Afxole.h için STDAFX.h dosyasındaki bir içerme yönergesi  
  
-   Uygulaması `DllGetClassObject` çağıran işlevi **AfxDllGetClassObject** işlevi  
  
-   Uygulaması `DllCanUnloadNow` çağıran işlevi **AfxDllCanUnloadNow** işlevi  
  
-   Uygulaması `DllRegisterServer` çağıran işlevi [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) işlevi  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Otomasyon Sunucuları](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)
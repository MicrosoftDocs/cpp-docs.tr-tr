---
title: DLL'de Otomasyon | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41c5f31a72cf734296ecb281e0785d415c8043a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
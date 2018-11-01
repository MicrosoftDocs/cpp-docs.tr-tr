---
title: DLL'de Otomasyon
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: b9d4f7a71ceb384069fcbef6bf791f0c5fd1b933
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536545"
---
# <a name="automation-in-a-dll"></a>DLL'de Otomasyon

MFC DLL Sihirbazı'nda Otomasyon seçeneğinin seçtiğinizde, sihirbaz, aşağıdaki sağlar:

- Bir başlatıcı nesne Açıklama Dili (. ODL) dosyası

- Bir Afxole.h STDAFX.h dosyası içindeki INCLUDE yönergesi

- Uygulanışı `DllGetClassObject` çağıran işlevi **AfxDllGetClassObject** işlevi

- Uygulanışı `DllCanUnloadNow` çağıran işlevi **AfxDllCanUnloadNow** işlevi

- Uygulanışı `DllRegisterServer` çağıran işlevi [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) işlevi

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Otomasyon Sunucuları](../mfc/automation-servers.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)
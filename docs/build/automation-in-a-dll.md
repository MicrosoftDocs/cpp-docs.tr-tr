---
title: DLL'de Otomasyon
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: 4ac60c44348ea21f490cb312285ae88ac682cf7d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341661"
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

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)

---
description: "Daha fazla bilgi edinin: DLL 'de Otomasyon"
title: DLL'de Otomasyon
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: e0d6d0beec71f3994f6e726c6946b2069d1b081b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163242"
---
# <a name="automation-in-a-dll"></a>DLL'de Otomasyon

MFC DLL sihirbazında Otomasyon seçeneğini belirlediğinizde, sihirbaz size şunları sağlar:

- Bir başlangıç nesnesi Açıklama Dili (. ODL) dosyası

- Afxole. h için STDADFX. h dosyasındaki bir içerme yönergesi

- `DllGetClassObject` **AfxDllGetClassObject** işlevini çağıran işlevin uygulanması

- , `DllCanUnloadNow` **AfxDllCanUnloadNow** işlevini çağıran işlevin uygulanması

- `DllRegisterServer` [Copaobjectfactory:: öğenize kaydedilecektir](../mfc/reference/coleobjectfactory-class.md#updateregistryall) işlevini çağıran işlevin uygulanması

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Otomasyon sunucuları](../mfc/automation-servers.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)

---
title: DLL'de Otomasyon
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: dedc832d6726dccf8c0c2e88f9f4d5c67590c1c2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220924"
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

[Visual Studio'da C/C++ DLL'leri oluşturma](dlls-in-visual-cpp.md)

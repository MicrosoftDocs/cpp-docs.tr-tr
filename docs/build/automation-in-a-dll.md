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
ms.openlocfilehash: cde5d0e400f1bdd3f5a851d47da581380273b04a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717798"
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
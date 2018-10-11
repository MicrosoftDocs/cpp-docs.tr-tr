---
title: FreeLibrary ve AfxFreeLibrary | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs:
- C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a86300b4814c8712f3cf88f91421dc1d0842e8a7
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081530"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary ve AfxFreeLibrary

Bir DLL çağrı açıkça bir bağlantı işlemleri [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) DLL Modulü artık gerekli olmadığında işlev. Bu modülün başvuru sayısını azaltır işlev ve başvuru sayısı sıfır olursa, işlemin adres alanından eşlemesini.

Bir MFC uygulamasında [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) yerine `FreeLibrary` bir MFC uzantılı DLL kaldırılamıyor. ' % S'arabirimi (işlev prototipi) için `AfxFreeLibrary` aynı `FreeLibrary`.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [DLL'ye örtük olarak bağlama](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Hangi bağlama yönteminin kullanılacağını belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [LoadLibrary ve AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
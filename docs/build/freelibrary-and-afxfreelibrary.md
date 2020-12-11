---
description: 'Daha fazla bilgi edinin: FreeLibrary ve AfxFreeLibrary'
title: FreeLibrary ve AfxFreeLibrary
ms.date: 11/04/2016
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
ms.openlocfilehash: ea4da8c69aa663add85e740d99b68731e263b442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162800"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary ve AfxFreeLibrary

Bir DLL 'ye açıkça bağlanan süreçler, DLL modülüne artık gerek kalmadığında [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) işlevini çağırır. Bu işlev, modülün başvuru sayısını azaltır. Ve başvuru sayısı sıfırsa, işlemin adres alanından eşlenmemiş olur.

Bir MFC uygulamasında, bir MFC uzantı DLL 'sini kaldırmak için yerine [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) ' i kullanın `FreeLibrary` . İçin arabirim (işlev prototipi) `AfxFreeLibrary` ile aynıdır `FreeLibrary` .

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)\
[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)\
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)

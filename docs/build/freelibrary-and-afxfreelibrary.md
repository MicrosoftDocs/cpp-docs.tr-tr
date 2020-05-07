---
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
ms.openlocfilehash: 0b530aca2ab036de186ff3fdb11be23f41e12d05
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821557"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary ve AfxFreeLibrary

Bir DLL 'ye açıkça bağlanan süreçler, DLL modülüne artık gerek kalmadığında [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) işlevini çağırır. Bu işlev, modülün başvuru sayısını azaltır. Ve başvuru sayısı sıfırsa, işlemin adres alanından eşlenmemiş olur.

Bir MFC uygulamasında, bir MFC uzantı DLL 'sini kaldırmak `FreeLibrary` Için yerine [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) ' i kullanın. İçin `AfxFreeLibrary` Arabirim (işlev prototipi) ile `FreeLibrary`aynıdır.

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

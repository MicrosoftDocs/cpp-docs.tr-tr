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
ms.openlocfilehash: 9c657bb0d583270f81658afa53f36b1be6a4fd4a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493258"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary ve AfxFreeLibrary

Bir DLL 'ye açıkça bağlanan süreçler, DLL modülüne artık gerek kalmadığında [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) işlevini çağırır. Bu işlev, modülün başvuru sayısını azaltır ve başvuru sayısı sıfır ise, işlemin adres alanından eşlemelerden kaldırır.

Bir MFC uygulamasında, bir MFC uzantı dll 'sini kaldırmak `FreeLibrary` için yerine [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) ' i kullanın. İçin `AfxFreeLibrary` Arabirim (işlev prototipi) ile `FreeLibrary`aynıdır.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'daC++ C/dll oluşturma](dlls-in-visual-cpp.md)<br/>
[](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)FreeLibrary
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)

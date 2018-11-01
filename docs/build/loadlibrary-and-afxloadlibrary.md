---
title: LoadLibrary ve AfxLoadLibrary
ms.date: 05/24/2018
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: 7c0b63d80a8b4b03b55d6e50af6c08a8de0937de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596560"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary ve AfxLoadLibrary

İşler çağrı [LoadLibraryExA](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) veya [LoadLibraryExW](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexw)(veya [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) bir DLL'ye açıkça bağlanmak için. İşlev başarılı olursa, belirtilen DLL'yi çağıran işlemin adres alanına eşler ve diğer işlevlerle açık bağlamada kullanılan DLL için bir tanıtıcı döndürür; Örneğin, `GetProcAddress` ve `FreeLibrary`.

`LoadLibrary` örtük bağlama için kullanılanla aynı arama sırasını kullanarak DLL'yi bulmaya çalışır. Sistem DLL'yi bulamazsa ya da giriş noktası işlevi FALSE döndürürse, `LoadLibrary` NULL döndürür. Çağrı `LoadLibrary` çağıran işlemin adres alanına eşlenmiş bir DLL modülü belirtiyorsa işlev modülün başvuru sayısını artırır ve DLL bir tanıtıcı döndürür.

DLL giriş noktası işlevi varsa, işletim sistemini çağıran iş parçacığının bağlamında işlevi çağırır. `LoadLibrary`. DLL, önceki arama nedeniyle işleme zaten bağlıysa, giriş noktası işlevi çağrılmaz `LoadLibrary` karşılık gelen hiçbir çağrısına sahip `FreeLibrary` işlevi.

MFC uzantı DLL'leri yükleyen MFC uygulamaları için biz kullanmanızı öneririz. `AfxLoadLibrary` yerine `LoadLibrary`. `AfxLoadLibrary` iş parçacığı eşitlemesini işler çağırmadan önce `LoadLibrary`. ' % S'arabirimi (işlev prototipi) için `AfxLoadLibrary` aynı `LoadLibrary`.

Windows, DLL'yi yükleyemezse işlem hatadan kurtarmayı dener. Örneğin, işlem hatası kullanıcıyı uyarır ve kullanıcıdan başka bir DLL yolu belirtin.

> [!IMPORTANT]
> DLL'lerin tam yolunu belirttiğinizden emin olun. Dosyalar yüklendiğinde geçerli dizin ilk aranır. Dosya yolunu nitelendirmezseniz, hedeflenen bir olmayan bir dosya yüklenebilir. Bunu önlemek için başka bir yolu kullanmaktır [/DEPENDENTLOADFLAG](../build/reference/dependentloadflag.md) bağlayıcı seçeneği.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [DLL'ye örtük olarak bağlama](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Hangi bağlama yönteminin kullanılacağını belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order)

- [FreeLibrary ve AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)

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
ms.openlocfilehash: c7700dd865e320686a2ad8bd036f207b9ecee6ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493217"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary ve AfxLoadLibrary

İşlem bir DLL 'ye açıkça bağlanmak için [Loadlibraryexa](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) veya [Loadlibraryexw](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) (veya [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) çağrısını çağırır. İşlev başarılı olursa, belirtilen DLL 'yi çağıran işlemin adres alanına eşler ve DLL 'ye, Açık bağlama içindeki diğer işlevlerle birlikte kullanılabilecek bir tanıtıcı döndürür — Örneğin, `GetProcAddress` ve. `FreeLibrary`

`LoadLibrary`örtük bağlama için kullanılan aynı arama dizisini kullanarak DLL 'yi bulmaya çalışır. Sistem DLL 'yi bulamazsa veya giriş noktası işlevi false döndürürse, `LoadLibrary` null değerini döndürür. Çağrısı, çağıran işlemin `LoadLibrary` adres alanına eşlenmiş bir dll modülü belirtiyorsa, işlev dll 'nin işleyicisini döndürür ve modülün başvuru sayısını artırır.

DLL 'de bir giriş noktası işlevi varsa, işletim sistemi işlevini çağıran iş parçacığı `LoadLibrary`bağlamında çağırır. `LoadLibrary` Bu, `FreeLibrary` işlevine karşılık gelen hiçbir çağrısı olmayan önceki bir çağrı nedeniyle, dll zaten işleme eklenmişse, giriş noktası işlevi çağrılmaz.

MFC uzantı dll 'lerini yükleyen MFC uygulamaları için `AfxLoadLibrary` `LoadLibrary`yerine kullanmanızı öneririz. `AfxLoadLibrary`çağrısı `LoadLibrary`yapmadan önce iş parçacığı eşitlemesini işler. İçin arabirim (işlev prototipi) ile `AfxLoadLibrary` `LoadLibrary`aynıdır.

Windows DLL 'yi yükleyemediğinden, işlem hatadan kurtarmayı deneyebilir. Örneğin, işlem hatayı kullanıcıya bildirebilir ve kullanıcıdan DLL için başka bir yol belirtmesini ister.

> [!IMPORTANT]
> Tüm dll 'Lerin tam yolunu belirttiğinizden emin olun. Dosyalar yüklendiğinde, geçerli dizin ilk olarak aranır. Dosyanın yolunu nitelendirmeyin, amaçlanan bir dosya yüklü olabilir. Bunu önlemenin bir diğer yolu da [/Dependentloadflag](reference/dependentloadflag.md) bağlayıcı seçeneğini kullanmaktır.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary ve AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio 'daC++ C/dll oluşturma](dlls-in-visual-cpp.md)

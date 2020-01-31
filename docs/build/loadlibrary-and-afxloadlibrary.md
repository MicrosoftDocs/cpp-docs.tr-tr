---
title: LoadLibrary ve AfxLoadLibrary
description: MSVC ' de dll 'lerin açık yüklemesi için LoadLibrary ve AfxLoadLibrary kullanma.
ms.date: 01/28/2020
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: f803212c4485f7517dc42802f1ff581ffa4e609d
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821544"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary ve AfxLoadLibrary

İşlem bir DLL 'ye açıkça bağlanmak için [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) veya [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) çağrısını çağırır. (MFC uygulamaları [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary) veya [Afxloadlibraryex](../mfc/reference/application-information-and-management.md#afxloadlibraryex)kullanır.) İşlev başarılı olursa, belirtilen DLL 'yi çağıran işlemin adres alanına eşleştirir ve DLL 'ye bir tanıtıcı döndürür. Tanıtıcı, Açık bağlama için kullanılan diğer işlevlerde gereklidir — Örneğin, `GetProcAddress` ve `FreeLibrary`. Daha fazla bilgi için bkz. [Açık bağlama](linking-an-executable-to-a-dll.md#linking-explicitly).

`LoadLibrary`, örtük bağlama için kullanılan arama dizisini kullanarak DLL 'yi bulmaya çalışır. `LoadLibraryEx`, arama yolu sırası üzerinde daha fazla denetim sağlar. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı arama sırası](/windows/win32/dlls/dynamic-link-library-search-order). Sistem DLL 'yi bulamazsa veya giriş noktası işlevi FALSE döndürürse `LoadLibrary` NULL değeri döndürür. `LoadLibrary` çağrısı, çağıran işlemin adres alanına eşlenmiş bir DLL modülü belirtiyorsa, işlev DLL 'nin işleyicisini döndürür ve modülün başvuru sayısını artırır.

DLL 'de bir giriş noktası işlevi varsa, işletim sistemi işlevi `LoadLibrary` veya `LoadLibraryEx`çağıran iş parçacığı bağlamında çağırır. DLL zaten işleme eklenmişse, giriş noktası işlevi çağrılmaz. Bu, DLL için daha önceki bir `LoadLibrary` veya `LoadLibraryEx` çağrısının `FreeLibrary` işlevine karşılık gelen bir çağrısı olmadığında meydana gelir.

MFC uzantı dll 'Lerini yükleyen MFC uygulamaları için `LoadLibrary` veya `LoadLibraryEx`yerine `AfxLoadLibrary` veya `AfxLoadLibraryEx` kullanmanızı öneririz. MFC işlevleri, DLL 'yi açıkça yüklemeden önce iş parçacığı eşitlemesini işler. `AfxLoadLibrary` ve `AfxLoadLibraryEx` için arabirimler (işlev prototipleri) `LoadLibrary` ve `LoadLibraryEx`aynıdır.

Windows DLL 'yi yükleyemiyorum, işleminiz hatadan kurtarmayı deneyebilir. Örneğin, hatayı kullanıcıya bildirebilir ve sonra DLL için başka bir yol sorabilir.

> [!IMPORTANT]
> Tüm dll 'Lerin tam yolunu belirttiğinizden emin olun. Dosyalar `LoadLibrary`tarafından yüklendiğinde, geçerli dizin ilk olarak aranabilir. Dosyanın yolunu tam olarak nitelendirmezseniz, amaçlanan bir dosya yüklenmiş olabilir. Bir DLL oluşturduğunuzda, statik olarak bağlanmış DLL bağımlılıkları için bir arama sırası belirtmek üzere [/Dependentloadflag](reference/dependentloadflag.md) bağlayıcı seçeneğini kullanın. Dll 'leriniz içinde, açıkça yüklenen bağımlılıklara yönelik tüm yolları kullanın ve `LoadLibraryEx` veya `AfxLoadLibraryEx` modül arama sırasını belirtmek için çağrı parametreleri yapın. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı güvenliği](/windows/win32/dlls/dynamic-link-library-security) ve [dinamik bağlantı kitaplığı arama sırası](/windows/win32/dlls/dynamic-link-library-search-order).

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)

- [FreeLibrary ve AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio 'daC++ C/dll oluşturma](dlls-in-visual-cpp.md)

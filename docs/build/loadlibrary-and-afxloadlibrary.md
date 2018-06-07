---
title: LoadLibrary ve AfxLoadLibrary | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- LoadLibrary
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc3be5d374995c657021952184794f146c37f4dc
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753594"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary ve AfxLoadLibrary

İşler çağrısı [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) (veya [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) açıkça bir DLL'e bağlanmak için. İşlev başarılı olursa, belirtilen DLL çağırma işlemi adres alanına eşler ve diğer işlevleri açıkça bağlamada ile kullanılan DLL için bir işleyici döner — Örneğin, `GetProcAddress` ve `FreeLibrary`.

`LoadLibrary` örtük olarak bağlama için kullanılanla aynı arama sırasını kullanarak DLL bulmaya çalışır. Sistem DLL'yi bulamazsa veya giriş noktası işlevi FALSE döndürürse `LoadLibrary` NULL döndürür. Varsa çağrısı `LoadLibrary` arama işlemi adres alanına zaten eşleştirilmiş bir DLL modülü belirtir işlevi bir tanıtıcı artırır ve DLL modülü başvurusu sayısını döndürür.

DLL bir giriş noktası işlevi varsa işletim sistemi çağıran iş parçacığının bağlamında işlevi çağırır `LoadLibrary`. DLL, önceki çağrısı nedeniyle işleme zaten bağlıysa, giriş noktası işlevi çağrılmaz `LoadLibrary` karşılık gelen hiçbir çağrısına sahip `FreeLibrary` işlevi.

MFC uzantı DLL'leri yükleme MFC uygulamaları için kullanmanızı öneririz `AfxLoadLibrary` yerine `LoadLibrary`. `AfxLoadLibrary` işler iş parçacığı eşitleme çağırmadan önce `LoadLibrary`. (İşlev prototipi) arabirimine `AfxLoadLibrary` aynı `LoadLibrary`.

Windows DLL yüklenemiyorsa, işlem hatadan kurtarmak deneyebilirsiniz. Örneğin, işlem hata kullanıcıya bildirmek ve dll Dosyasının başka bir yolu belirtmesini isteyin.

> [!IMPORTANT]  
> DLL'lerin tam yolunu belirttiğinizden emin olun. Dosyalar yüklendiğinde geçerli dizinin ilk aranır. Dosya yolunu uygun değil, hedeflenen değil bir dosyası yüklenmiş. Bunu önlemek için başka bir yolu kullanmaktır [/DEPENDENTLOADFLAG](../build/reference/dependentloadflag.md) bağlayıcı seçeneği.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir DLL'e örtük olarak bağlanma](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Dinamik bağlantı kitaplığı arama sırası](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)

- [FreeLibrary ve AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)
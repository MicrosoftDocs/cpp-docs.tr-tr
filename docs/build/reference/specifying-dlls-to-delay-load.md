---
title: Gecikme Yükü DLL'lerini Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: 2b6737abd76c03186881e83bbd2bf286be6ffe2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318153"
---
# <a name="specifying-dlls-to-delay-load"></a>Gecikme Yükü DLL'lerini Belirtme

Geciktirilecek dll ile yük belirtebilirsiniz [/delayload](delayload-delay-load-import.md):`dllname` bağlayıcı seçeneği. Kendi yardımcı işlevi sürümünüzü kullanmayı planlamıyorsanız, programınızı delayimp.lib (için Masaüstü uygulamalar için) veya dloadhelper.lib (mağaza uygulamaları için) ile de bağlamanız gerekir.

Gecikmeli DLL yükleme basit bir örneği verilmiştir:

```
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

Proje hata ayıklama sürümünü oluşturun. Hata ayıklayıcı ve fark edersiniz, user32.dll çağrısı yaptığınızda yüklendiği kullanarak kod aracılığıyla adım `MessageBox`.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](linker-support-for-delay-loaded-dlls.md)

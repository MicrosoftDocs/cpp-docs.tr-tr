---
title: Gecikme yükü DLL'lerini belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e9becc0a686d3add5db140b239f1997f81a45be
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722585"
---
# <a name="specifying-dlls-to-delay-load"></a>Gecikme Yükü DLL'lerini Belirtme

Geciktirilecek dll ile yük belirtebilirsiniz [/delayload](../../build/reference/delayload-delay-load-import.md):`dllname` bağlayıcı seçeneği. Kendi yardımcı işlevi sürümünüzü kullanmayı planlamıyorsanız, programınızı delayimp.lib (için Masaüstü uygulamalar için) veya dloadhelper.lib (mağaza uygulamaları için) ile de bağlamanız gerekir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)
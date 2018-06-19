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
ms.openlocfilehash: a7756499ddf24055feb1c540df13fbe8249edf42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373728"
---
# <a name="specifying-dlls-to-delay-load"></a>Gecikme Yükü DLL'lerini Belirtme
Gecikme DLL'leri ile yük belirtebilirsiniz [/delayload](../../build/reference/delayload-delay-load-import.md):`dllname` bağlayıcı seçeneği. Kendi yardımcı bir işlev sürümünü kullanmayı planlıyorsanız değil, delayimp.lib (için Masaüstü uygulamaları) veya (mağaza uygulamaları için) dloadhelper.lib programınızla bağlamanız gerekir.  
  
 DLL Gecikmeli yükleme basit bir örnek verilmiştir:  
  
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
  
 Projenin hata ayıklama sürümü oluşturun. Hata ayıklayıcı ve görürsünüz yalnızca çağrısı yaptığınızda bu user32.dll yüklenen kod kullanarak aracılığıyla adım `MessageBox`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)
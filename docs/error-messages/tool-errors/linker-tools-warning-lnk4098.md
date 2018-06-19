---
title: Bağlayıcı araçları uyarısı LNK4098 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4098
dev_langs:
- C++
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8aadf25d968d6d457f891cab49a43591455b9d12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301713"
---
# <a name="linker-tools-warning-lnk4098"></a>Bağlayıcı Araçları Uyarısı LNK4098
DEFAULTLIB 'Kitaplığı' çakışıyor diğer kitaplıklar kullanın; /NODEFAULTLIB:library kullanın  
  
 Uyumsuz kitaplıklarıyla bağlamak çalışıyorsunuz.  
  
> [!NOTE]
>  Çalışma zamanı kitaplıkları artık farklı karıştırma önlemek için yönergeleri içerir. Bu farklı türleri kullanın veya hata ayıklama denerseniz, uyarı ve hata ayıklama olmayan sürümleri çalışma zamanı kitaplığı aynı programda alırsınız. Örneğin, bir tür çalışma zamanı kitaplığı ve başka bir başka bir tür (örneğin, tek iş parçacıklı karşı iş parçacıklı) kullanmak için dosya ve bunları bağlamak denenen kullanmak için bir dosya derlenmiş ise, bu uyarı alırsınız. Aynı çalışma zamanı kitaplığı kullanmak için tüm kaynak dosyaları derleme. Bkz: [çalışma zamanı kitaplığını kullan](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **/MT**, **/LD**) daha fazla bilgi için derleyici seçenekleri.  
  
 Bağlayıcı'nın kullanabilirsiniz [/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md) bağlayıcı arama hangi kitaplıkların belirlemek için anahtar. Debug olmayan çalışma zamanı kitaplıkları, kullanın LNK4098 ve tek iş parçacıklı, kullanan bir yürütülebilir dosyası oluşturmak istiyorsanız alırsanız **/VERBOSE:LIB** bağlayıcı arama hangi kitaplıkların bulmak için seçeneği. Bağlayıcı LIBC.lib ve değil LIBCMT.lib, MSVCRT.lib, LIBCD.lib, LIBCMTD.lib veya MSVCRTD.lib aranır kitaplıkları yazdırma. Bağlayıcı kullanarak yanlış çalışma zamanı kitaplıkları yoksay anlayabilirsiniz [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) yoksay istediğiniz her kitaplığın.  
  
 Aşağıdaki tabloda, hangi kitaplıkların kullanmak istediğiniz hangi çalışma zamanı kitaplığı bağlı olarak dikkate alınması gösterilmektedir.  
  
|Bu çalışma zamanı kitaplığı kullanmak için|Bu kitaplıklar yoksay|  
|-----------------------------------|----------------------------|  
|Tek iş parçacıklı (libc.lib)|Libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|(Libcmt.lib) birden çok iş parçacıklı|libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|DLL (msvcrt.lib) kullanarak birden çok iş parçacıklı|libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|  
|Tek iş parçacıklı (libcd.lib) hata ayıklama|libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|  
|Birden çok iş parçacıklı hata ayıklama (libcmtd.lib)|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|  
|DLL (msvcrtd.lib) kullanarak Multithreaded hata ayıklama|libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|  
  
 Örneğin, bu uyarıyı alınan ve çalışma zamanı kitaplıkları olmayan-debug, tek iş parçacıklı sürümünü kullanan bir yürütülebilir dosya oluşturmak istediğiniz bağlayıcı ile aşağıdaki seçenekleri kullanabilirsiniz:  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```
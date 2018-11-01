---
title: Bağlayıcı Araçları Uyarısı LNK4098
ms.date: 11/04/2016
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 088124fcce7cafad3fab3280ae0b3ae0d893283e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468724"
---
# <a name="linker-tools-warning-lnk4098"></a>Bağlayıcı Araçları Uyarısı LNK4098

defaultlib 'library' çakışıyor diğer kitaplıkların kullanımı; / nodefaultlıb: library kullanın

Uyumsuz kitaplıklarıyla bağlayın çalışıyorsunuz.

> [!NOTE]
>  Çalışma zamanı kitaplıkları artık farklı türlerini karıştırmak önlemek için yönergeleri içerir. Bu farklı türleri kullanın veya hata ayıklama çalışırsanız, uyarı ve Çalışma Zamanı Kitaplığı'nın hata ayıklamasız sürümleri aynı programda alırsınız. Örneğin, çalışma zamanı tür kitaplığı ve başka bir başka bir tür (örneğin, tek ve birden çok iş parçacıklı iş parçacıklı) kullanmak için dosya ve bunları bağlamak çalıştığınız kullanmak için bir dosya derlenmiş ise, bu uyarı alırsınız. Aynı çalışma zamanı kitaplığı kullanmak için tüm kaynak dosyaları derlemeniz gerekir. Bkz: [çalışma zamanı kitaplığını kullan](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **/MT**, **/LD**) daha fazla bilgi için derleyici seçenekleri.

Bağlayıcı'nın kullanabileceğiniz [: LIB](../../build/reference/verbose-print-progress-messages.md) bağlayıcı arama hangi kitaplıkların belirlemek için anahtar. Hata ayıklama olmayan çalışma zamanı kitaplıkları, kullanın LNK4098 ve tek iş parçacıklı, kullanan bir yürütülebilir dosyası oluşturmak istiyorsanız alırsanız **: LIB** bağlayıcı arama hangi kitaplıkların bulmak için seçeneği. Bağlayıcı /ML ve değil LIBCMT.lib, MSVCRT.lib, LIBCD.lib, Lıbcmtd.lib veya MSVCRTD.lib Aranan kitaplıklar yazdırma. Bağlayıcı kullanarak hatalı bir çalışma zamanı kitaplıkları yoksay söyleyebilirsiniz [/nodefaultlıb](../../build/reference/nodefaultlib-ignore-libraries.md) yoksay istediğiniz her bir kitaplık için.

Aşağıdaki tabloda, hangi kitaplıkların bağlı olarak hangi çalışma zamanı kitaplığı kullanmak istediğiniz yoksayılıp yoksayılmaması gerektiğini gösterir.

|Bu çalışma zamanı kitaplığını kullanma|Bu kitaplıkları yoksay|
|-----------------------------------|----------------------------|
|Tek iş parçacıklı (/ML)|LIBCMT.lib msvcrt.lib, libcd.lib lıbcmtd.lib, msvcrtd.lib|
|Çok iş parçacıklı (LIBCMT.lib)|/ML msvcrt.lib, libcd.lib lıbcmtd.lib, msvcrtd.lib|
|Çok iş parçacıklı DLL (msvcrt.lib) kullanma|/ML LIBCMT.lib, libcd.lib lıbcmtd.lib, msvcrtd.lib|
|Tek iş parçacıklı (libcd.lib) hata ayıklama|/ML LIBCMT.lib, msvcrt.lib lıbcmtd.lib, msvcrtd.lib|
|Hata ayıklama çok iş parçacıklı (lıbcmtd.lib)|/ML LIBCMT.lib, msvcrt.lib libcd.lib, msvcrtd.lib|
|Çok iş parçacıklı DLL (msvcrtd.lib) kullanarak hata ayıklama|/ML LIBCMT.lib, msvcrt.lib libcd.lib, lıbcmtd.lib|

Örneğin, bu uyarı aldığınızı ve çalışma zamanı kitaplıklarının hata ayıklama olmayan, tek iş parçacıklı sürümünü kullanan bir yürütülebilir dosya oluşturmak istediğiniz bağlayıcı ile aşağıdaki seçenekleri kullanabilirsiniz:

```
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```
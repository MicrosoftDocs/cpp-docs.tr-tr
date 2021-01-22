---
description: Gecikme Yükleme Yardımcısı işlevi hakkında daha fazla bilgi edinin
title: Gecikme yükleme yardımcısı işlevini anlayın
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.openlocfilehash: a4b25a51af25458f5add5ed7eb3fd58f759dae7b
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667248"
---
# <a name="understand-the-delay-load-helper-function"></a>Gecikme yükleme yardımcısı işlevini anlayın

Bağlayıcı için yardımcı işlev-desteklenen Gecikmeli yükleme, çalışma zamanında DLL 'yi gerçekten yükler. Davranışını özelleştirmek için yardımcı işlevini değiştirebilirsiniz: içinde sağlanan yardımcı işlevini kullanmak yerine *`delayimp.lib`* , kendi işlevinizi yazıp programınıza bağlayın. Bir yardımcı işlev, tüm Gecikmeli yüklenen dll 'Leri sunar.

DLL veya içeri aktarmalar adına göre belirli işlemler yapmak istiyorsanız, kendi yardımcı işlevinizin bir sürümünü sağlayabilirsiniz.

Yardımcı işlevi şu işlemleri gerçekleştirir:

- Zaten yüklenmiş olup olmadığını görmek için kitaplığa depolanmış tanıtıcıyı denetler

- `LoadLibrary`DLL yüklemeyi denemek için çağrılar

- `GetProcAddress`Yordamın adresini almayı denemek için çağrılar

- Şimdi yüklenen giriş noktasını çağırmak için Gecikmeli içeri aktarma yük dönüşmesini döndürür

Yardımcı işlevi, aşağıdaki eylemlerden her birini gerçekleştirdikten sonra programınızdaki bir bildirim kancasını geri çağırabilir:

- Yardımcı işlev başladığında

- `LoadLibrary`Yardımcı işlevinde yalnızca Before çağrılır

- `GetProcAddress`Yardımcı işlevinde yalnızca Before çağrılır

- `LoadLibrary`Yardımcı işlevindeki çağrısı başarısız olursa

- `GetProcAddress`Yardımcı işlevindeki çağrısı başarısız olursa

- Yardımcı işlevi işlemi tamamlandıktan sonra

Bu kanca noktalarından her biri, gecikme içeri aktarma yük dönüşöğesine geri dönmesinin dışında, yardımcı yordamın normal işlemesini bir şekilde değiştiren bir değer döndürebilir.

Varsayılan yardımcı kod *`Delayhlp.cpp`* ve *`Delayimp.h`* (VC *`include`* dizininde) içinde bulunabilir ve içinde *`Delayimp.lib`* (VC *`lib`* dizininde) derlenir. Kendi yardımcı işlevinizi yazmadığınız takdirde bu kitaplığı derlemelerine eklemeniz gerekir.

Aşağıdaki makaleler yardımcı işlevini anlatmaktadır:

- [Visual C++ 6.0 sonrasındaki gecikmeli yükleme yardımcısı işlevi DLL değişiklikleri](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [Çağırma kuralları, parametreler ve dönüş türü](calling-conventions-parameters-and-return-type.md)

- [Yapı ve sabit tanımları](structure-and-constant-definitions.md)

- [Gerekli değerleri hesapla](calculating-necessary-values.md)

- [Gecikmeli yüklenen DLL 'i açıkça kaldırma](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)

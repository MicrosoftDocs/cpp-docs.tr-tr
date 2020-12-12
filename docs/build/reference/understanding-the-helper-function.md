---
description: 'Hakkında daha fazla bilgi edinin: yardımcı Işlevini anlama'
title: Yardımcı İşlevini Anlama
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
ms.openlocfilehash: d47e392d78d6cf872af28b992885c57d34bddf0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247104"
---
# <a name="understanding-the-helper-function"></a>Yardımcı İşlevini Anlama

Bağlayıcı için yardımcı işlev-desteklenen Gecikmeli yükleme, çalışma zamanında DLL 'yi gerçekten yükler. Kendi işlevinizi yazarak ve Delayimp. lib içinde sağlanan yardımcı işlevini kullanmak yerine programınıza bağlayarak davranışını özelleştirmek için yardımcı işlevini değiştirebilirsiniz. Bir yardımcı işlev, tüm Gecikmeli yüklenen dll 'Leri sunar.

DLL veya içeri aktarmalar adına göre belirli işlemler yapmak istiyorsanız, kendi yardımcı işlevinizin bir sürümünü sağlayabilirsiniz.

Yardımcı işlevi aşağıdaki eylemleri gerçekleştirir:

- Zaten yüklenmiş olup olmadığını görmek için kitaplığa depolanmış tanıtıcıyı denetler

- DLL yüklemeyi denemek için **LoadLibrary** çağırır

- Yordamın adresini almayı denemek için **GetProcAddress** çağırır

- Şimdi yüklenen giriş noktasını çağırmak için Gecikmeli içeri aktarma yük dönüşmesini döndürür

Yardımcı işlevi, aşağıdaki eylemlerden her birini gerçekleştirdikten sonra programınızdaki bir bildirim kancasını geri çağırabilir:

- Yardımcı işlev başladığında

- Yardım işlevinde **LoadLibrary** çağrılmadan hemen önce

- Yardımcı işlevinde **GetProcAddress** çağrılmadan hemen önce

- Yardımcı işlevinde **LoadLibrary** öğesine çağrı başarısız olduysa

- Yardımcı işlevinde **GetProcAddress** çağrısı başarısız olduysa

- Yardımcı işlevi işlemi tamamlandıktan sonra

Bu kanca noktalarından her biri, gecikme içeri aktarma yük dönüşöğesine geri dönmesinin dışında, yardımcı yordamın normal işlemesini bir şekilde değiştirecek bir değer döndürebilir.

Varsayılan yardımcı kod, delayhlp. cpp ve Delayimp. h içinde bulunabilir (vc\include içinde) ve Delayimp. lib içinde derlenir (vc\lib içinde). Kendi yardımcı işlevinizi yazmadığınız takdirde bu kitaplığı derlemelerine eklemeniz gerekir.

Aşağıdaki konular yardımcı işlevini anlatmaktadır:

- [Visual C++ 6,0 ' den sonra DLL geciken Yükleme Yardımcısı Işlevinde değişiklikler](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [Çağırma kuralları, parametreler ve dönüş türü](calling-conventions-parameters-and-return-type.md)

- [Yapı ve sabit tanımları](structure-and-constant-definitions.md)

- [Gerekli değerler hesaplanıyor](calculating-necessary-values.md)

- [Delay-Loaded DLL 'yi kaldırma](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)

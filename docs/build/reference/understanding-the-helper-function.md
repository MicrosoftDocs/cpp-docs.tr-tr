---
title: Yardımcı işlevini anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90ca214b28296417ab80341232c08a55b92adff4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725501"
---
# <a name="understanding-the-helper-function"></a>Yardımcı İşlevini Anlama

Bağlayıcı tarafından desteklenen Gecikmeli Yükleme Yardımcısı işlevi ne aslında DLL çalışma zamanında yükler ' dir. Kendi işlev yazma ve Delayimp.lib içinde sağlanan yardımcı işlevini kullanmak yerine, programınız için bağlama davranışını özelleştirmek için yardımcı işlevini değiştirebilirsiniz. Tüm Gecikmeli yüklenen DLL'ler bir yardımcı işlevini görür.

DLL içeri aktarmaları ve adlarına göre belirli bir işlemeyi yapmak istiyorsanız, kendi yardımcı işlevi sürümünüzü sağlayabilirsiniz.

Yardımcı işlevini aşağıdaki eylemleri gerçekleştirir:

- Bunu önceden yüklenip yüklenmediğini görmek için kitaplığa depolanmış tanıtıcı denetler

- Çağrıları **LoadLibrary** DLL yükleme girişiminde

- Çağrıları **GetProcAddress** yordamı adresini alma denemek için

- Şimdi yüklenen giriş noktasını çağırmak için dönüştürücü gecikme alınacak döndürür yükleme

Yardımcı işlevini geri için bir bildirim kanca programınızdaki her birinden sonra aşağıdaki eylemlerden birini çağırabilirsiniz:

- Yardımcı işlevini başladığında

- Hemen önce **LoadLibrary** yardımcı işlev çağrılır

- Hemen önce **GetProcAddress** yardımcı işlev çağrılır

- Çağrı **LoadLibrary** yardımcı işlevi başarısız oldu

- Çağrı **GetProcAddress** yardımcı işlevi başarısız oldu

- Sonra yardımcı işlevi yapılır işleme

Bunların her biri bağlama noktaları normal işleme gecikmesi alma yük dönüştürücü dön dışında bir yolla Yardımcısı yordamının değiştirecek bir değer döndürebilir.

Varsayılan yardımcı kod Delayhlp.cpp ve Delayimp.h (vc\include içinde) bulunabilir ve içinde Delayimp.lib (vc\lib içinde) derlenir. Kendi yardımcı işlevinizi yazmadığınız sürece bu kitaplık, derlemelerde dahil etmek gerekir.

Aşağıdaki konularda yardımcı işlevini açıklanmaktadır:

- [Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [Çağırma Kuralları, Parametreler ve Dönüş Türü](../../build/reference/calling-conventions-parameters-and-return-type.md)

- [Yapı ve Sabit Tanımları](../../build/reference/structure-and-constant-definitions.md)

- [Gereken Değerleri Hesaplama](../../build/reference/calculating-necessary-values.md)

- [Gecikmeli Yüklenen DLL'i Kaldırma](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)
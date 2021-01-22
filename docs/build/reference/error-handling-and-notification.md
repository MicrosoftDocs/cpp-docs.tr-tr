---
title: Hata işleme ve bildirme
description: 'Hakkında daha fazla bilgi edinin: DLL Gecikmeli yükleme hatası işleme ve bildirim'
ms.date: 01/19/2021
helpviewer_keywords:
- error handling, and notification
ms.openlocfilehash: a0161814a07bd5bbedbaa6d13c7c32cd3aeab559
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666959"
---
# <a name="error-handling-and-notification"></a>Hata işleme ve bildirme

Programınız Gecikmeli yüklenen dll 'Ler kullanıyorsa, program çalışırken meydana gelen hatalar işlenmemiş özel durumlara neden olacağı için robustly hataları işlemelidir. Hata işleme iki bölümden oluşur: bir kanca üzerinden kurtarma ve bir özel durum aracılığıyla raporlama.

DLL gecikmesi yükleme hatası işleme ve bildirimi hakkında daha fazla bilgi için bkz. [yardımcı Işlevini anlama](understanding-the-helper-function.md).

Kanca işlevleri hakkında daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](structure-and-constant-definitions.md).

## <a name="recovery-through-a-hook"></a>Kanca üzerinden kurtarma

Kodunuzun bir hata üzerinde kurtarılması veya alternatif bir kitaplık ya da yordam sağlaması gerekebilir. Yardımcı işleve, alternatif kodu sağlayabilecek veya durumu ortadan kaldırmanın bir kancasını sağlayabilirsiniz. Kanca yordamının uygun bir değer döndürmesi gerekir, böylece işlem devam edebilir (bir `HINSTANCE` veya `FARPROC` ). Ya da bir özel durumun oluşturulması gerektiğini göstermek için 0 döndürebilir. Ayrıca kendi özel durumunu veya `longjmp` kancasını de oluşturabilir. Bildirim kancaları ve hata kancaları vardır.

## <a name="reporting-via-an-exception"></a>Özel durum aracılığıyla raporlama

Hatayı işlemek için gerekli olan tüm işlemler yordamı iptal etmek ise, Kullanıcı kodu özel durumu işleyebileceği sürece hiçbir kanca gerekmez.

Aşağıdaki makalelerde hata işleme ve bildirim ele alınmaktadır:

- [Bildirim kancaları](notification-hooks.md)

- [Hata kancaları](failure-hooks.md)

- [DLL gecikmesi yükleme özel durum kodları](exceptions-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)

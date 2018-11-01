---
title: Hata İşleme ve Bildirme
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 845a79e035943dbbde0d498702f70ec7dd6b4d3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432410"
---
# <a name="error-handling-and-notification"></a>Hata İşleme ve Bildirme

Hata işleme ve bildirme hakkında daha fazla bilgi için bkz. [yardımcı işlevini anlama](understanding-the-helper-function.md).

Kanca işlevlerini raporlama hakkında daha fazla bilgi için bkz. [yapı ve sabit tanımları](../../build/reference/structure-and-constant-definitions.md).

Programınızı Gecikmeli yüklenen DLL'ler kullanıyorsa, program çalışırken oluşan hata işlenmeyen özel durumları sonuçlanır olduğundan, hataları yerine işlemesi gerekir. Hata işleme iki bölümünü oluşur:

Bir kancası aracılığıyla kurtarma.
Kodunuzu kurtarmak veya diğer kitaplığı ve/veya yordamı hatası sağlamak gerekiyorsa bir kanca sağladığınız veya durumu ortadan kaldırmak için yardımcı işlevini sağlanabilir. Kanca rutin gerekir böylece işleme uygun bir değer döndürür (HINSTANCE veya FARPROC bir) devam edebilir veya bir özel durum olduğunu göstermek için 0. Ayrıca kendi özel durum oluşturabilir veya **longjmp** kanca dışında. Bildirim kancaları ve hata kancaları vardır.

Bir özel durum raporlama.
Tüm hata işleme için gerekli olan ise yordamı iptal etmek için kullanıcı kodu özel durumu işleyebilecek sürece hiçbir kanca gereklidir.

Hata işleme ve bildirme aşağıdaki konular açıklanmaktadır:

- [Bildirim Kancaları](../../build/reference/notification-hooks.md)

- [Hata Kancaları](../../build/reference/failure-hooks.md)

- [Özel Durumlar](../../build/reference/exceptions-c-cpp.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)
---
title: Hata İşleme ve Bildirme
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 29fe46e15712609ec0c4f268749aaefed103117e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812947"
---
# <a name="error-handling-and-notification"></a>Hata İşleme ve Bildirme

Hata işleme ve bildirme hakkında daha fazla bilgi için bkz. [yardımcı işlevini anlama](understanding-the-helper-function.md).

Kanca işlevlerini raporlama hakkında daha fazla bilgi için bkz. [yapı ve sabit tanımları](structure-and-constant-definitions.md).

Programınızı Gecikmeli yüklenen DLL'ler kullanıyorsa, program çalışırken oluşan hata işlenmeyen özel durumları sonuçlanır olduğundan, hataları yerine işlemesi gerekir. Hata işleme iki bölümünü oluşur:

Bir kancası aracılığıyla kurtarma.
Kodunuzu kurtarmak veya diğer kitaplığı ve/veya yordamı hatası sağlamak gerekiyorsa bir kanca sağladığınız veya durumu ortadan kaldırmak için yardımcı işlevini sağlanabilir. Kanca rutin gerekir böylece işleme uygun bir değer döndürür (HINSTANCE veya FARPROC bir) devam edebilir veya bir özel durum olduğunu göstermek için 0. Ayrıca kendi özel durum oluşturabilir veya **longjmp** kanca dışında. Bildirim kancaları ve hata kancaları vardır.

Bir özel durum raporlama.
Tüm hata işleme için gerekli olan ise yordamı iptal etmek için kullanıcı kodu özel durumu işleyebilecek sürece hiçbir kanca gereklidir.

Hata işleme ve bildirme aşağıdaki konular açıklanmaktadır:

- [Bildirim Kancaları](notification-hooks.md)

- [Hata Kancaları](failure-hooks.md)

- [Özel Durumlar](exceptions-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](linker-support-for-delay-loaded-dlls.md)

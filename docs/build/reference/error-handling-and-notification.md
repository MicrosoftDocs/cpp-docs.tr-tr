---
description: 'Hakkında daha fazla bilgi edinin: hata Işleme ve bildirim'
title: Hata İşleme ve Bildirme
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 234d50d0b4a7e8b81874d1926ac056f8cba23376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200994"
---
# <a name="error-handling-and-notification"></a>Hata İşleme ve Bildirme

Hata işleme ve bildirim hakkında daha fazla bilgi için bkz. [yardımcı Işlevini anlama](understanding-the-helper-function.md).

Kanca işlevleri hakkında daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](structure-and-constant-definitions.md).

Programınız Gecikmeli yüklenen dll 'Ler kullanıyorsa, program çalışırken oluşan hatalar işlenmemiş özel durumlara neden olacağı için robustly hataları işlemelidir. Hata işleme iki kısımdan oluşur:

Kanca üzerinden kurtarma.
Kodunuzun kurtarmak veya hata durumunda başka bir kitaplık ve/veya yordamı sağlaması gerekiyorsa, bu durumu sağlayabilecek veya ortadan kaldırmanıza yardımcı işleve bir kanca sağlanması gerekebilir. Bir özel durumun oluşturulması gerektiğini göstermek için, kanca yordamının uygun bir değer döndürmesi gerekir, böylece işleme devam edebilir (bir HINSTANCE veya FARPROC) veya 0. Ayrıca, kendi özel durumunu veya daha sonra da **longjmp** 'yi oluşturabilir. Bildirim kancaları ve hata kancaları vardır.

Özel durum ile raporlama.
Hatayı işlemek için gerekli olan tüm işlemler yordamı iptal etmek ise, Kullanıcı kodu özel durumu işleyebileceği sürece hiçbir kanca gerekmez.

Aşağıdaki konularda hata işleme ve bildirim ele alınmaktadır:

- [Bildirim kancaları](notification-hooks.md)

- [Hata kancaları](failure-hooks.md)

- [Özel durumlar](exceptions-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)

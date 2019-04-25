---
title: Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: b6e514a6b13aced4fcd765df091810504f948588
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176258"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği

MSVC bağlayıcı artık DLL'lerin Gecikmeli yüklemeyi destekler. Bu Windows SDK'sı işlevleri gerek kalmamasını **LoadLibrary** ve **GetProcAddress** Gecikmeli yükleme DLL uygulamak için.

Visual C++ 6.0 önce çalışma zamanında bir DLL'yi tek yolu kullanmaktı **LoadLibrary** ve **GetProcAddress**; işletim sistemi DLL'yi yüklemeye, yürütülebilir veya onu yüklenen DLL kullanarak.

Örtük olarak bir DLL ile bağlanırken Visual C++ 6.0 ile başlayarak, programın bu DLL içinde bir işlevi çağırır kadar gecikme seçenekleri DLL'yi sağlar.

Bir uygulama geciktirip kullanarak bir DLL yükleme [/delayload (gecikme yükleme içeri aktarma)](delayload-delay-load-import.md) yardımcı işlevini (Visual C++ tarafından sağlanan varsayılan uygulaması) ile bağlayıcı seçeneği. Yardımcısı işlevi DLL çalışma zamanında çağırarak yükleyecek **LoadLibrary** ve **GetProcAddress** sizin için.

Gecikmeli DLL, yükleme dikkate almanız gerekir:

- Programınız bir işlev DLL'de çağırmamanız.

- Bir DLL sonlarında kadar program yürütme, çağrılan işlev değil.

Bir DLL için Gecikmeli yüklemeye veya derleme sırasında belirtilebilir bir. EXE veya. DLL projesi. A. Bir veya daha fazla DLL'lerin yüklenmesini geciktirir DLL projesi kendisi bir Gecikmeli yüklenen giriş noktası Dllmain çağırmalıdır değil.

Aşağıdaki konular, DLL'leri yüklemede gecikme açıklar:

- [Gecikme Yükü DLL'lerini Belirtme](specifying-dlls-to-delay-load.md)

- [Gecikmeli Yüklenen DLL'i Açıkça Kaldırma](explicitly-unloading-a-delay-loaded-dll.md)

- [Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme](loading-all-imports-for-a-delay-loaded-dll.md)

- [İçeri Aktarılanları Bağlama](binding-imports.md)

- [Hata İşleme ve Bildirme](error-handling-and-notification.md)

- [Gecikmeli Yükleme İçe Aktarmalarını Dökme](dumping-delay-loaded-imports.md)

- [DLL'leri Yüklemede Gecikme Kısıtlamaları](constraints-of-delay-loading-dlls.md)

- [Yardımcı İşlevini Anlama](understanding-the-helper-function.md)

- [Kendi Yardımcı İşlevinizi Geliştirme](developing-your-own-helper-function.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](../dlls-in-visual-cpp.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)

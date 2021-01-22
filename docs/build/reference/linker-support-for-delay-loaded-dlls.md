---
description: "Daha fazla bilgi edinin: Gecikmeli yüklenen dll 'Ler için bağlayıcı desteği"
title: Gecikmeli yüklenen DLL'ler için bağlayıcı desteği
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.openlocfilehash: 9ae1e2c68ed59e742493a9098d98fc35d5f2a7c7
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667284"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Gecikmeli yüklenen DLL'ler için bağlayıcı desteği

MSVC Bağlayıcısı, dll 'lerin gecikmeli yüklenmesini destekler. Bu özellik, Windows SDK işlevlerini kullanma `LoadLibrary` ve `GetProcAddress` DLL gecikmeli yüklemeyi uygulama ihtiyacını sizi maliyetinden kurtarır.

Gecikmeli yük olmadan, çalışma zamanında DLL yüklemek için tek yol, `LoadLibrary` ve ' ı kullanmaktır `GetProcAddress` ; işletim sistemi, bu dosyayı kullanan ÇALıŞTıRıLABILIR veya DLL yüklendiğinde dll 'yi yükler.

Gecikmeli yük ile, bir DLL 'yi örtük olarak bağladığınızda bağlayıcı, program bu DLL 'de bir işlev çağırana kadar DLL yükünü geciktirmek için seçenekler sağlar.

Bir uygulama, bir yardımcı işlevle [ `/DELAYLOAD` (yük içeri aktarmayı geciktir)](delayload-delay-load-import.md) BAĞLAYıCı seçeneğini kullanarak dll yüklemeyi geciktirebilirler. (Varsayılan bir yardımcı işlev uygulamasını Microsoft tarafından sağlanır.) Yardımcı işlevi, ve ' i çağırarak çalışma zamanında DLL 'yi isteğe bağlı olarak yükler `LoadLibrary` `GetProcAddress` .

Şu durumlarda bir DLL yükleme gecikmesini göz önünde bulundurun:

- Programınız DLL 'de bir işlev çağırmayabilir.

- DLL 'deki bir işlev, programınızın yürütülmesine geç kadar çağrılamaz.

Bir DLL 'nin geciken yüklemesi, bir EXE veya DLL projesinin oluşturulması sırasında belirtilebilir. Bir veya daha fazla dll 'nin kendisini yüklemeyi geciktireeden bir DLL projesi içinde Gecikmeli yüklenen bir giriş noktası çağırmamalıdır `DllMain` .

Aşağıdaki makaleler dll 'Leri yükleme gecikmesini anlatmaktadır:

- [Yük gecikmesi için dll 'Leri belirtin](specifying-dlls-to-delay-load.md)

- [Gecikmeli yüklenen DLL 'i açıkça kaldırma](explicitly-unloading-a-delay-loaded-dll.md)

- [Gecikmeli yüklenen DLL için tüm içeri aktarmaları yükle](loading-all-imports-for-a-delay-loaded-dll.md)

- [Gecikmeli yüklenen içeri aktarmaları bağlama](binding-imports.md)

- [Hata işleme ve bildirme](error-handling-and-notification.md)

- [Gecikmeli yüklenen içeri aktarmalar dökümünü al](dumping-delay-loaded-imports.md)

- [DLL'leri yüklemede gecikme kısıtlamaları](constraints-of-delay-loading-dlls.md)

- [Yardımcı işlevini anlama](understanding-the-helper-function.md)

- [Kendi yardımcı işlevinizi geliştirme](developing-your-own-helper-function.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](../dlls-in-visual-cpp.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)

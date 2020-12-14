---
description: "Daha fazla bilgi: Delay-Loaded dll 'Ler için bağlayıcı desteği"
title: Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 6bf4527d14c7313874f162f0597114132b1a81cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190971"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği

MSVC Bağlayıcısı artık dll 'Lerin gecikmeli yüklemesini desteklemektedir. Bu sizi maliyetinden kurtarır, DLL Gecikmeli yükleme uygulamak için **LoadLibrary** ve **GetProcAddress** Windows SDK işlevlerini kullanma gereksinimleridir.

6,0 Visual C++ önce, çalışma zamanında DLL 'yi çalıştırmanın tek yolu **LoadLibrary** ve **GetProcAddress** kullanılarak yapılır; çalışan çalıştırılabilir veya DLL yüklendiğinde, işletim sistemi DLL 'yi yükler.

Visual C++ 6,0 ' den başlayarak, bir DLL ile dolaylı olarak bağlandığınızda bağlayıcı, bu DLL 'de bir işlev çağırana kadar DLL yükleme gecikmesi için seçenekler sağlar.

Bir uygulama bir yardımcı işlevle [/delayload (Gecikmeli yükleme Içeri aktarma)](delayload-delay-load-import.md) bağlayıcı SEÇENEĞINI kullanarak dll yüklemeyi geciktirebilir (varsayılan uygulama Visual C++ tarafından sağlanmış). Yardımcı işlevi, **LoadLibrary** ve **GETPROCADDRESS** 'i çağırarak dll 'yi çalışma zamanında yükler.

Şu durumlarda bir DLL yükleme gecikmesini göz önünde bulundurmanız gerekir:

- Programınız DLL 'de bir işlev çağırmayabilir.

- DLL 'deki bir işlev, programınızın yürütülmesine geç kadar çağrılamaz.

Bir DLL 'nin geciken yüklemesi, bir öğesinin derlemesi sırasında belirtilebilir. EXE veya. DLL projesi. A. Bir veya daha fazla dll 'nin yüklenmesini geciktirecek DLL projesi, DllMain 'de Gecikmeli yüklenen bir giriş noktasını çağırmalıdır.

Aşağıdaki konular dll 'Leri yükleme gecikmesini anlatmaktadır:

- [Gecikmeli yük için dll 'Leri belirtme](specifying-dlls-to-delay-load.md)

- [Delay-Loaded DLL 'sini açıkça kaldırma](explicitly-unloading-a-delay-loaded-dll.md)

- [Delay-Loaded DLL için tüm Içeri aktarmalar yükleniyor](loading-all-imports-for-a-delay-loaded-dll.md)

- [Bağlama Içeri aktarmaları](binding-imports.md)

- [Hata Işleme ve bildirim](error-handling-and-notification.md)

- [Delay-Loaded Içeri aktarmalar dökümünü alma](dumping-delay-loaded-imports.md)

- [Dll 'Leri yükleme gecikmesi kısıtlamaları](constraints-of-delay-loading-dlls.md)

- [Yardımcı Işlevini anlama](understanding-the-helper-function.md)

- [Kendi yardımcı Işlevinizi geliştirme](developing-your-own-helper-function.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](../dlls-in-visual-cpp.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)

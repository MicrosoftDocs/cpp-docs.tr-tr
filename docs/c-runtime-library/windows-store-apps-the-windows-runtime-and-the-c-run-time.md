---
title: UWP uygulamaları, Windows çalışma zamanı ve C çalışma zamanı
ms.date: 02/02/2019
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
ms.openlocfilehash: 932b5388f2d1bf87f0d77ae1330fa3e613c9dca7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385131"
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>UWP uygulamaları, Windows çalışma zamanı ve C çalışma zamanı

Evrensel Windows Platformu (UWP) uygulamaları, Windows 8'de yürüten Windows çalışma zamanı içinde çalışan programlardır. Windows çalışma zamanı işlevleri, değişkenler ve UWP uygulaması için kaynaklar denetleyen güvenilir bir ortamdır. Ancak, tasarım gereği, Windows çalışma zamanı kısıtlamalarını UWP uygulamalarında çoğu C çalışma zamanı kitaplığı (CRT) özelliklerinin kullanımını engelleyin.

Windows çalışma zamanı, aşağıdaki CRT özellikleri desteklemez:

- Desteklenmeyen işlevsellik ile ilgili birçok CRT işlevleri.

   Bir UWP uygulaması bir işlemi kullanarak örneğin, oluşturamazsınız **exec** ve **üretme** aileleri yordamları.

   Ne zaman bir CRT işlevini olgu, başvuru makalesinde not aldığınız bir UWP uygulamasında desteklenmiyor.

- En çok baytlı karakter ve dize işlevleri.

   Ancak, hem Unicode hem de ANSI metinler desteklenir.

- Ortam değişkenleri.

- Geçerli çalışma dizinine kavramı.

- UWP uygulamaları ve statik olarak CRT'ye bağlı ve kullanılarak oluşturulan DLL'ler [/MT](../build/reference/md-mt-ld-use-run-time-library.md) veya `/MTd` derleyici seçenekleri.

   Diğer bir deyişle, CRT çoklu iş parçacığı, statik bir sürümünü kullanan bir uygulama.

- Kullanılarak oluşturulan bir uygulamayı [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneği.

   Diğer bir deyişle, bir hata ayıklama, çoklu iş parçacıklı ve DLL'ye özgü CRT sürümü. Böyle bir uygulamayı Windows çalışma zamanı üzerinde desteklenmiyor.

Kullanılamayan bir UWP uygulaması ve diğer işlevler için öneriler, CRT işlevleri tam bir listesi için bkz. [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)<br/>
[Windows Çalışma Zamanı Desteklenmeyen CRT İşlevleri](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Evrensel Windows platformu konsol uygulaması oluşturma](/windows/uwp/launch-resume/console-uwp)

---
description: 'Daha fazla bilgi edinin: UWP uygulamaları, Windows Çalışma Zamanı ve C Run-Time'
title: UWP uygulamaları, Windows Çalışma Zamanı ve C Run-Time
ms.date: 02/02/2019
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
ms.openlocfilehash: cfbbdbde19b882fb51b8fd8782b20e4205bdb00b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136753"
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>UWP uygulamaları, Windows Çalışma Zamanı ve C Run-Time

Evrensel Windows Platformu (UWP) uygulamaları, Windows 8 ' de yürütülen Windows Çalışma Zamanı çalışan programlardır. Windows Çalışma Zamanı, UWP uygulaması için kullanılabilir işlevleri, değişkenleri ve kaynakları denetleyen güvenilir bir ortamdır. Ancak, tasarıma göre Windows Çalışma Zamanı kısıtlamalar UWP uygulamalarında çoğu C Run-Time Library (CRT) özelliğinin kullanılmasını önler.

Windows Çalışma Zamanı aşağıdaki CRT özelliklerini desteklemez:

- Desteklenmeyen işlevlerle ilgili çoğu CRT işlevi.

   Örneğin, UWP uygulaması, yordamları **Exec** ve **üretme** ailesinden bir işlem oluşturamaz.

   Bir UWP uygulamasında bir CRT işlevi desteklenmediği zaman, bu olgu başvuru makalesinde belirtilmiştir.

- Çok baytlı karakter ve dize işlevleri.

   Ancak, hem Unicode hem de ANSI metni desteklenir.

- Ortam değişkenleri.

- Geçerli bir çalışma dizini kavramı.

- CRT 'ye statik olarak bağlanan ve [/MT](../build/reference/md-mt-ld-use-run-time-library.md) veya derleyici seçenekleri KULLANıLARAK oluşturulan UWP uygulamaları ve DLL 'ler `/MTd` .

   Diğer bir deyişle, çok iş parçacıklı, CRT 'ın statik sürümünü kullanan bir uygulamadır.

- [/MDD](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneği kullanılarak oluşturulan bir uygulama.

   Yani, CRT 'nin bir hata ayıklama, çoklu iş parçacığı ve DLL 'ye özgü sürümüdür. Bu tür bir uygulama Windows Çalışma Zamanı desteklenmez.

UWP uygulamasında kullanılamayan CRT işlevlerinin tamamı ve alternatif işlevlere yönelik öneriler için bkz. [Evrensel Windows platformu uygulamalarda desteklenmeyen crt işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)<br/>
[Desteklenmeyen CRT Işlevleri Windows Çalışma Zamanı](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Evrensel Windows Platformu konsol uygulaması oluşturma](/windows/uwp/launch-resume/console-uwp)

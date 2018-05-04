---
title: UWP uygulamaları, Windows çalışma zamanı ve C çalışma zamanı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29e1a67ce57e4ddf726ba64923bbe5a95b5b2f1c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>UWP uygulamaları, Windows çalışma zamanı ve C çalışma zamanı

Evrensel Windows Platformu (UWP) uygulamaları üzerinde yürütür Windows çalışma zamanı çalışan programlardır [!INCLUDE[win8](../build/reference/includes/win8_md.md)]. Windows çalışma zamanı işlevleri, değişkenleri ve bir UWP uygulaması kullanılabilir kaynaklar denetleyen güvenilir bir ortamdır. Ancak, tasarım gereği, Windows çalışma zamanı kısıtlamaları UWP uygulamalarında çoğu C çalışma zamanı kitaplığı (CRT) özellikleri kullanımını engeller.

Windows çalışma zamanı aşağıdaki CRT özellikleri desteklemez:

- Desteklenmeyen işlevsellik ilgili çoğu CRT işlevleri.

   Bir UWP uygulaması bir işlemi kullanarak örneğin, oluşturamazsınız **exec** ve **spawn** yordamları aileleri.

   Ne zaman olgu kendi başvurusu makalesinde not aldığınız bir UWP uygulamasında CRT işlevi desteklenmiyor.

- En çok baytlı karakter ve dize işlevleri.

   Ancak, Unicode ve ANSI text desteklenir.

- Konsol uygulamaları ve komut satırı bağımsız değişkenleri.

   Ancak, geleneksel masaüstü uygulamaları hala konsol ve komut satırı bağımsız değişkenleri destekler.

- Ortam değişkenleri.

- Geçerli çalışma dizini kavramı.

- UWP uygulamalar ve statik olarak CRT bağlı ve kullanılarak oluşturulmuş DLL'leri [/MT](../build/reference/md-mt-ld-use-run-time-library.md) veya `/MTd` derleyici seçenekleri.

   Diğer bir deyişle, CRT çoklu iş parçacığı, statik bir sürümünü kullanan bir uygulama.

- Kullanılarak oluşturulmuş bir uygulama [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneği.

   Diğer bir deyişle, bir hata ayıklama, çoklu iş parçacığı kullanan ve CRT DLL özgü sürümü. Bu tür bir uygulamayı Windows çalışma zamanı'desteklenmiyor.

UWP uygulama ve önerileri alternatif işlevleri için kullanılamayan CRT işlevleri tam bir listesi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)<br/>
[Windows Çalışma Zamanı Desteklenmeyen CRT İşlevleri](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>

---
description: 'Hakkında daha fazla bilgi edinin: Module-Definition (. Def) dosyaları'
title: Modül-Tanımlama (.Def) Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: d52141a2917b2c82616597b2d070a84b96d1a653
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137819"
---
# <a name="module-definition-def-files"></a>Modül-Tanımlama (.Def) Dosyaları

Modül tanım (. def) dosyaları, bağlayıcı için dışarı aktarmalar, öznitelikler ve bağlanacak program hakkında bilgi sağlar. Bir. def dosyası bir DLL derlerken en yararlı seçenektir. Modül tanımı deyimleri yerine kullanılabilecek [MSVC bağlayıcı seçenekleri](linker-options.md) olduğundan,. def dosyaları genellikle gerekli değildir. Ayrıca, [__declspec (dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md) öğesini, dışarıya aktarılmış işlevleri belirtmek için bir yol olarak da kullanabilirsiniz.

[/Def (Module-Definition dosyası belirt)](def-specify-module-definition-file.md) bağlayıcı seçeneğini kullanarak bağlayıcı aşamasında bir. def dosyası çağırabilirsiniz.

Dışarı aktarma işlemi olmayan bir. exe dosyası oluşturuyorsanız, bir. def dosyası kullanmak, çıkış dosyanızı daha büyük ve daha yavaş yükleme yapar.

Bir örnek için bkz. [def dosyaları kullanarak dll 'Den dışarı aktarma](../exporting-from-a-dll-using-def-files.md).

Daha fazla bilgi için aşağıdaki bölümlere bakın:

- [Module-Definition deyimleri için kurallar](rules-for-module-definition-statements.md)

- [AKTARıMLARı](exports.md)

- [HEAPSIZE](heapsize.md)

- [LIBRARY](library.md)

- [AD](name-c-cpp.md)

- [BAŞLıKLı](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [STUB](stub.md)

- [Sürüm](version-c-cpp.md)

- [Ayrılmış sözcükler](reserved-words.md)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](c-cpp-building-reference.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)

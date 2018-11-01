---
title: Modül-Tanımlama (.Def) Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: a882d71e76b961fefb7059bee8634507f12f7986
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460443"
---
# <a name="module-definition-def-files"></a>Modül-Tanımlama (.Def) Dosyaları

Modül-tanımlama (.def) dosyaları, bağlayıcı dışarı aktarma, öznitelikleri ve bağlanacak programı hakkında diğer bilgiler hakkında bilgi sağlar. Bir .def dosyası bir DLL'yi oluştururken en kullanışlıdır. Olduğundan [bağlayıcı seçenekleri](../../build/reference/linker-options.md) kullanılabilecek modül tanımlama deyimleri yerine .def dosyaları genellikle gerekli değildir. Ayrıca [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) belirtmek için bir yol dışa aktarılan işlevleri.

Bir .def dosyası ile bağlayıcı aşamasında çağırabilirsiniz [/def (modül tanım dosyası belirtin)](../../build/reference/def-specify-module-definition-file.md) bağlayıcı seçeneği.

Bir .def dosyası kullanarak, hiçbir dışarı sahip bir .exe dosyası oluşturuyorsanız çıktı dosyası daha büyük ve daha yavaş yükleniyor hale getirir.

Bir örnek için bkz. [bir DLL kullanarak DEF dosyaları dışarı aktarma](../../build/exporting-from-a-dll-using-def-files.md).

Daha fazla bilgi için aşağıdaki bölümlere bakın:

- [Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)

- [EXPORTS](../../build/reference/exports.md)

- [HEAPSIZE](../../build/reference/heapsize.md)

- [LIBRARY](../../build/reference/library.md)

- [ADI](../../build/reference/name-c-cpp.md)

- [BÖLÜMLERİ](../../build/reference/sections-c-cpp.md)

- [STACKSIZE](../../build/reference/stacksize.md)

- [STUB](../../build/reference/stub.md)

- [SÜRÜM](../../build/reference/version-c-cpp.md)

- [Ayrılmış sözcükler](../../build/reference/reserved-words.md)

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
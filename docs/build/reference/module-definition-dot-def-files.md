---
title: Modül-Tanımlama (.Def) Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: 0047f24722644cd9a68bbbf827ced26ad085d4c1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812245"
---
# <a name="module-definition-def-files"></a>Modül-Tanımlama (.Def) Dosyaları

Modül-tanımlama (.def) dosyaları, bağlayıcı dışarı aktarma, öznitelikleri ve bağlanacak programı hakkında diğer bilgiler hakkında bilgi sağlar. Bir .def dosyası bir DLL'yi oluştururken en kullanışlıdır. Olduğundan [MSVC bağlayıcı seçenekleri](linker-options.md) kullanılabilecek modül tanımlama deyimleri yerine .def dosyaları genellikle gerekli değildir. Ayrıca [__declspec(dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md) belirtmek için bir yol dışa aktarılan işlevleri.

Bir .def dosyası ile bağlayıcı aşamasında çağırabilirsiniz [/def (modül tanım dosyası belirtin)](def-specify-module-definition-file.md) bağlayıcı seçeneği.

Bir .def dosyası kullanarak, hiçbir dışarı sahip bir .exe dosyası oluşturuyorsanız çıktı dosyası daha büyük ve daha yavaş yükleniyor hale getirir.

Bir örnek için bkz. [bir DLL kullanarak DEF dosyaları dışarı aktarma](../exporting-from-a-dll-using-def-files.md).

Daha fazla bilgi için aşağıdaki bölümlere bakın:

- [Modül Tanımlama Deyimleri Kuralları](rules-for-module-definition-statements.md)

- [EXPORTS](exports.md)

- [HEAPSIZE](heapsize.md)

- [LIBRARY](library.md)

- [ADI](name-c-cpp.md)

- [BÖLÜMLERİ](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [STUB](stub.md)

- [SÜRÜM](version-c-cpp.md)

- [Ayrılmış sözcükler](reserved-words.md)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)

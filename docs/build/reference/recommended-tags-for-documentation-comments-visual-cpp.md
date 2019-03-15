---
title: Belge açıklamaları (C++ belgeleri açıklamaları) için önerilen etiketler
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: adb8440dc07f8f3e193b58be6782859fbb8413e4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823711"
---
# <a name="recommended-tags-for-documentation-comments"></a>Belge Açıklamaları için Önerilen Etiketler

MSVC derleyicisi, kodunuzda belge açıklamalarını işle ve her derlenecek bir .xdc dosyasını oluşturur ve xdcmake.exe'yi .xdc dosyalarına bir .xml dosyası işleme. Belgeleri oluşturmak için .xml dosyası işleme sitenizde uygulanması gereken bir ayrıntı olur.

Etiketler, yapıları türleri gibi işlenir ve tür üyelerini.

Etiketler, tür veya üyeler hemen gelmelidir.

> [!NOTE]
>  Belge açıklamaları özellikler ve olaylar için satır tanımı dışında bir ad alanına veya uygulanamaz; Belge açıklamaları-sınıf bildirimlerinde gerekir.

Derleyici, geçerli bir XML değil herhangi bir etiket işleyecektir. Aşağıdaki kullanıcı belgeleri, yaygın olarak kullanılan işlevsellik sağlar:

||||
|-|-|-|
|[\<c >](c-visual-cpp.md)|[\<kod >](code-visual-cpp.md)|[\<Örnek >](example-visual-cpp.md)|
|[\<Özel Durum >](exception-visual-cpp.md)1|[\<Ekle >](include-visual-cpp.md)1|[\<listesi >](list-visual-cpp.md)|
|[\<para >](para-visual-cpp.md)|[\<param >](param-visual-cpp.md)1|[\<paramref >](paramref-visual-cpp.md)1|
|[\<izni >](permission-visual-cpp.md)1|[\<REMARKS >](remarks-visual-cpp.md)|[\<döndürür >](returns-visual-cpp.md)|
|[\<bkz: >](see-visual-cpp.md)1|[\<SeeAlso >](seealso-visual-cpp.md)1|[\<Summary >](summary-visual-cpp.md)|
|[\<Değer >](value-visual-cpp.md)|||

1. Derleyici sözdizimini doğrular.

Geçerli sürümde MSVC derleyicisi desteklemediği `<paramref>`, diğer Visual Studio derleyicileri tarafından desteklenen bir etiket. Visual C++ destekleyebilir `<paramref>` gelecek sürümlerden birinde.

## <a name="see-also"></a>Ayrıca Bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
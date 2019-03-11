---
title: Belge Açıklamaları için Önerilen Etiketler (Visual C++)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 154cb36ca121fee8731ac4e71506f562abb79988
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744803"
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Belge Açıklamaları için Önerilen Etiketler (Visual C++)

Visual C++ derleyicisi, kodunuzda belge açıklamalarını işle ve her derlenecek bir .xdc dosyasını oluşturur ve xdcmake.exe'yi .xdc dosyalarına bir .xml dosyası işleme. Belgeleri oluşturmak için .xml dosyası işleme sitenizde uygulanması gereken bir ayrıntı olur.

Etiketler, yapıları türleri gibi işlenir ve tür üyelerini.

Etiketler, tür veya üyeler hemen gelmelidir.

> [!NOTE]
>  Belge açıklamaları özellikler ve olaylar için satır tanımı dışında bir ad alanına veya uygulanamaz; Belge açıklamaları-sınıf bildirimlerinde gerekir.

Derleyici, geçerli bir XML değil herhangi bir etiket işleyecektir. Aşağıdaki kullanıcı belgeleri, yaygın olarak kullanılan işlevsellik sağlar:

||||
|-|-|-|
|[\<c >](../ide/c-visual-cpp.md)|[\<kod >](../ide/code-visual-cpp.md)|[\<Örnek >](../ide/example-visual-cpp.md)|
|[\<Özel Durum >](../ide/exception-visual-cpp.md)1|[\<Ekle >](../ide/include-visual-cpp.md)1|[\<listesi >](../ide/list-visual-cpp.md)|
|[\<para >](../ide/para-visual-cpp.md)|[\<param >](../ide/param-visual-cpp.md)1|[\<paramref >](../ide/paramref-visual-cpp.md)1|
|[\<izni >](../ide/permission-visual-cpp.md)1|[\<REMARKS >](../ide/remarks-visual-cpp.md)|[\<döndürür >](../ide/returns-visual-cpp.md)|
|[\<bkz: >](../ide/see-visual-cpp.md)1|[\<SeeAlso >](../ide/seealso-visual-cpp.md)1|[\<Summary >](../ide/summary-visual-cpp.md)|
|[\<Değer >](../ide/value-visual-cpp.md)|||

1. Derleyici sözdizimini doğrular.

Geçerli sürümde, Visual C++ derleyicisi tarafından desteklenmeyen `<paramref>`, diğer Visual Studio derleyicileri tarafından desteklenen bir etiket. Visual C++ destekleyebilir `<paramref>` gelecek sürümlerden birinde.

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)

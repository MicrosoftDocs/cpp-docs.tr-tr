---
title: Dokümantasyon Yorumları için Önerilen Etiketler (C++ dokümantasyon yorumları)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 1648d0eb019a3aad25641d7f6a7edd1ba26acf7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336167"
---
# <a name="recommended-tags-for-documentation-comments"></a>Belge Açıklamaları için Önerilen Etiketler

MSVC derleyicisi kodunuzda belge yorumlarını işleyecek ve her derleme için bir .xdc dosyası oluşturur ve xdcmake.exe .xdc dosyalarını bir .xml dosyasına işler. Belge oluşturmak için .xml dosyasını işlemek, sitenizde uygulanması gereken bir ayrıntıdır.

Etiketler, tür ve tür üyeleri gibi yapılarda işlenir.

Etiketler, türlerden veya üyelerden hemen önce olmalıdır.

> [!NOTE]
> Belge açıklamaları bir ad alanına veya özellikler ve olaylar için satır tanımı dışında uygulanamaz; belgeleme yorumları sınıf içi bildirimler üzerinde olmalıdır.

Derleyici, geçerli olan herhangi bir etiketi XML'i işler. Aşağıdaki etiketler, kullanıcı belgelerinde yaygın olarak kullanılan işlevselliği sağlar:

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<kod>](code-visual-cpp.md)|[\<örnek>](example-visual-cpp.md)|
|istisna>1 [ \< ](exception-visual-cpp.md)|>1 dahil [ \< ](include-visual-cpp.md)|[\<liste>](list-visual-cpp.md)|
|[\<para>](para-visual-cpp.md)|param>1 [ \< ](param-visual-cpp.md)|paramref>1 [ \< ](paramref-visual-cpp.md)|
|izin>1 [ \< ](permission-visual-cpp.md)|[\<açıklamalar>](remarks-visual-cpp.md)|[\<>döndürür](returns-visual-cpp.md)|
|bkz>1 [ \< ](see-visual-cpp.md)|seealso>1 [ \< ](seealso-visual-cpp.md)|[\<özet>](summary-visual-cpp.md)|
|[\<değer>](value-visual-cpp.md)|||

1. Derleyici sözdizimini doğrular.

Geçerli sürümde, MSVC derleyicisi, diğer Visual Studio derleyicileri tarafından desteklenen bir etiketi desteklemez. `<paramref>` Visual C++ `<paramref>` gelecekteki bir sürümde destekleyebilir.

## <a name="see-also"></a>Ayrıca bkz.

[XML Dokümantasyon](xml-documentation-visual-cpp.md)

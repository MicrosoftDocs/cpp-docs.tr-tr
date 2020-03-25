---
title: Belge açıklamaları için önerilen Etiketler (C++ belge açıklamaları)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 4e0937b79012f65ba136e18ac81f014be23688f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168869"
---
# <a name="recommended-tags-for-documentation-comments"></a>Belge Açıklamaları için Önerilen Etiketler

MSVC derleyicisi kodunuzda belge açıklamalarını işleyecek ve her compiland için bir. xdc dosyası oluşturduğunda ve xdcmake. exe. xdc dosyalarını bir. xml dosyasına işleyecek. Belge oluşturmak için. xml dosyasının işlenmesi, sitenizde uygulanması gereken ayrıntıdır.

Etiketler türler ve tür üyeleri gibi yapılar üzerinde işlenir.

Etiketler, türlerin veya üyelerin hemen önüne gelmelidir.

> [!NOTE]
>  Belge açıklamaları, Özellikler ve olaylar için bir ad alanına veya satır dışı tanıma uygulanamaz; Belge açıklamaları sınıf içi bildirimlerde olmalıdır.

Derleyici geçerli XML olan herhangi bir etiketi işleyecek. Aşağıdaki Etiketler kullanıcı belgelerinde yaygın olarak kullanılan işlevleri sağlar:

||||
|-|-|-|
|[\<c >](c-visual-cpp.md)|[\<kodu >](code-visual-cpp.md)|[\<örnek >](example-visual-cpp.md)|
|[\<özel durum >](exception-visual-cpp.md)1|[\<içerme >](include-visual-cpp.md)1|[\<listesi >](list-visual-cpp.md)|
|[\<paragraf >](para-visual-cpp.md)|[\<param >](param-visual-cpp.md)1|[\<paramref >](paramref-visual-cpp.md)1|
|[\<izin >](permission-visual-cpp.md)1|[\<açıklamalar >](remarks-visual-cpp.md)|[\<returns>](returns-visual-cpp.md)|
|[\<bkz. >](see-visual-cpp.md)1|[\<seede >](seealso-visual-cpp.md)1|[\<summary>](summary-visual-cpp.md)|
|[\<value>](value-visual-cpp.md)|||

1. Derleyici söz dizimini doğrular.

Geçerli sürümde, MSVC derleyicisi diğer Visual Studio derleyicileri tarafından desteklenen bir etiketi `<paramref>`desteklemez. Visual C++ , gelecekteki sürümlerde `<paramref>` destekleyebilir.

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)

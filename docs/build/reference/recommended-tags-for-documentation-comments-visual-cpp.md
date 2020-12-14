---
description: 'Hakkında daha fazla bilgi edinin: belge açıklamaları için önerilen Etiketler'
title: Belge açıklamaları için önerilen Etiketler (C++ belgeleri açıklamaları)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 34bae4043231abed87770aec252303bd99707afe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225355"
---
# <a name="recommended-tags-for-documentation-comments"></a>Belge Açıklamaları için Önerilen Etiketler

MSVC derleyicisi kodunuzda belge açıklamalarını işleyecek ve her compiland için bir. xdc dosyası oluşturacak ve xdcmake.exe. xdc dosyalarını bir. xml dosyasına işleyecek. Belge oluşturmak için. xml dosyasının işlenmesi, sitenizde uygulanması gereken ayrıntıdır.

Etiketler türler ve tür üyeleri gibi yapılar üzerinde işlenir.

Etiketler, türlerin veya üyelerin hemen önüne gelmelidir.

> [!NOTE]
> Belge açıklamaları, Özellikler ve olaylar için bir ad alanına veya satır dışı tanıma uygulanamaz; Belge açıklamaları sınıf içi bildirimlerde olmalıdır.

Derleyici geçerli XML olan herhangi bir etiketi işleyecek. Aşağıdaki Etiketler kullanıcı belgelerinde yaygın olarak kullanılan işlevleri sağlar:

[`<c>`](c-visual-cpp.md)
[`<code>`](code-visual-cpp.md)
[`<example>`](example-visual-cpp.md)
[`<exception>`](exception-visual-cpp.md)<sup></sup> 
 1 [`<include>`](include-visual-cpp.md) <sup></sup> 
 [`<list>`](list-visual-cpp.md) 1 
 [`<para>`](para-visual-cpp.md) 
 [`<param>`](param-visual-cpp.md) <sup></sup> 
 1 [`<paramref>`](paramref-visual-cpp.md) <sup></sup> 
 1 [`<permission>`](permission-visual-cpp.md) <sup></sup> 
 [`<remarks>`](remarks-visual-cpp.md) 1 
 [`<returns>`](returns-visual-cpp.md) 
 [`<see>`](see-visual-cpp.md) <sup></sup> 
 1 [`<seealso>`](seealso-visual-cpp.md) <sup>1</sup>
[`<summary>`](summary-visual-cpp.md)
[`<value>`](value-visual-cpp.md)

1. Derleyici söz dizimini doğrular.

Geçerli sürümde, MSVC derleyicisi `<paramref>` diğer Visual Studio derleyicileri tarafından desteklenen bir etiketi desteklemez. Visual C++ gelecek sürümlerde destekleyebilir `<paramref>` .

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)

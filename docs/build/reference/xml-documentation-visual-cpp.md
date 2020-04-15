---
title: XML Belgeleri (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
ms.openlocfilehash: c25c54e81bb9c10fc871a2abc178f57e661ae4e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335728"
---
# <a name="xml-documentation-visual-c"></a>XML Belgeleri (Visual C++)

Visual C++'da, kaynak kodunuza .xml dosyasına işlenecek yorumlar ekleyebilirsiniz. Bu dosya daha sonra, kodunuzdaki sınıflar için belge oluşturan bir işleme giriş olabilir.

Visual C++ kod dosyasında, XML dokümantasyon yorumları bir yöntem veya tür tanımından önce doğrudan bulunmalıdır. Yorumlar, IntelliSense QuickInfo veri ipucunu aşağıdaki senaryolarda doldurmak için kullanılabilir:

1. kod, eşlik eden .winmd dosyasına sahip bir Windows Runtime bileşeni olarak derlendiğinde

1. kaynak kodu geçerli projeye dahil edildiğinde

1. tür bildirimleri ve uygulamaları aynı üstbilgi dosyasında bulunan bir kütüphanede

> [!NOTE]
> Geçerli sürümde, kod yorumları şablonlar veya şablon türü içeren herhangi bir şey (örneğin, şablon olarak parametre alan bir işlev) üzerinde işlenmez. Bu tür yorumların eklenmesi tanımlanmamış davranışlara neden olur.

Belge açıklamaları içeren bir .xml dosyası oluşturma yla ilgili ayrıntılar için aşağıdaki konulara bakın.

|Hakkında bilgi için|Bkz.|
|---------------------------|---------|
|Kullanılacak derleyici seçenekleri|[/doc](doc-process-documentation-comments-c-cpp.md)|
|Belgelerde sık kullanılan işlevselliği sağlamak için kullanabileceğiniz etiketler|[Dokümantasyon Yorumları için Önerilen Etiketler](recommended-tags-for-documentation-comments-visual-cpp.md)|
|Derleyicinin kodunuzdaki yapıları tanımlamak için ürettiği kimlik dizeleri|[.xml Dosyasını İşle](dot-xml-file-processing.md)|
|Belge etiketleri nasıl sınırlandırılı|[Visual C++ Belge Etiketleri için Sınırlayıcılar](delimiters-for-visual-cpp-documentation-tags.md)|
|Bir veya daha fazla .xdc dosyasından .xml dosyası oluşturma.|[XDCMake Başvurusu](xdcmake-reference.md)|
|Visual Studio özellik alanlarıyla ilgili olarak XML hakkındaki bilgilere bağlantılar|[Görsel Stüdyo'da XML](/visualstudio/xml-tools/xml-tools-in-visual-studio)|

Bir belge açıklama metnine XML özel karakterler koymanız gerekiyorsa, XML varlıkları veya CDATA bölümünü kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../../extensions/component-extensions-for-runtime-platforms.md)

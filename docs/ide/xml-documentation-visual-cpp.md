---
title: XML Belgeleri (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
ms.openlocfilehash: 380fe73bba71d08bb9315e218f5946a7cf935108
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523892"
---
# <a name="xml-documentation-visual-c"></a>XML Belgeleri (Visual C++)

Visual C++'da bir .xml dosyasına işlenecek kaynak kodunuza yorum ekleyebilirsiniz. Bu dosya daha sonra kodunuzda sınıfları için belgeleri oluşturan bir işlem girişi olabilir.

Bir Visual C++ kod dosyasında XML belgeleri yorumları doğrudan yöntem veya tür tanımı önce bulunmalıdır. Açıklamalar, aşağıdaki senaryolarda IntelliSense Hızlıbilgi veri ipucu doldurmak için kullanılabilir:

1. kod ile eşlik eden bir .winmd dosyası bir Windows çalışma zamanı bileşeni olarak ne zaman derlenir

1. Kaynak kodu geçerli projedeki zaman dahildir

1. Kitaplıkta, tür bildirimleri ve uygulamalar aynı üstbilgi dosyasında bulunur

> [!NOTE]
>  Geçerli sürümde, kod açıklamaları şablonları ya da bir şablon türü (örneğin, bir şablon olarak bir parametre alan bir işlev) içeren herhangi bir şey işlenmez. Bu açıklama eklemek tanımsız davranışlara neden.

Belge açıklamaları bir .xml dosyası oluşturma hakkında daha fazla bilgi edinmek için aşağıdaki konulara bakın.

|Hakkında bilgi için|Bkz. |
|---------------------------|---------|
|Kullanılacak derleyici seçenekleri|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|
|Yaygın olarak sağlamak için kullanabileceğiniz etiket işlevleri belgelerinde kullanılır.|[Belge Açıklamaları için Önerilen Etiketler](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|
|Derleyici, kodunuzda yapıları tanımlamak için üreten kimliği dizesi|[.Xml dosyası işleme](../ide/dot-xml-file-processing.md)|
|Belge etiketleri sınırlandırmak nasıl|[Visual C++ Belge Etiketleri için Sınırlayıcılar](../ide/delimiters-for-visual-cpp-documentation-tags.md)|
|Bir veya daha fazla .xdc dosyalarının bir .xml dosyası oluşturuluyor.|[XDCMake Başvurusu](../ide/xdcmake-reference.md)|
|Visual Studio özellik alanlarına olarak XML hakkındaki bilgiler için bağlantılarla ilgili|[Visual Studio XML](/visualstudio/xml-tools/xml-tools-in-visual-studio)|

Özel karakterler XML belgeleri açıklama metninde koymak gerekiyorsa, XML varlıklar veya CDATA bölümü kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)
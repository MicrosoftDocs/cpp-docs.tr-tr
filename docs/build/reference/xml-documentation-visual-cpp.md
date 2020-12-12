---
description: 'Daha fazla bilgi edinin: XML belgeleri (Visual C++)'
title: XML Belgeleri (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
ms.openlocfilehash: 762380d08483292866cb96b34be4d85f7a2f510a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260949"
---
# <a name="xml-documentation-visual-c"></a>XML Belgeleri (Visual C++)

Visual C++, kaynak kodunuza bir. xml dosyasına işlenecek açıklamalar ekleyebilirsiniz. Bu dosya daha sonra kodunuzdaki sınıflar için belgeler oluşturan bir işlemin girişi olabilir.

Bir Visual C++ kod dosyasında, XML belge yorumlarının doğrudan bir yöntemden veya tür tanımından önce konumlandırılmaları gerekir. Açıklamalar, IntelliSense QuickInfo veri ipucunu aşağıdaki senaryolarda doldurmak için kullanılabilir:

1. kod, eşlik eden bir. winmd dosyası olan bir Windows Çalışma Zamanı bileşeni olarak derlenmişse

1. kaynak kodu geçerli projeye dahil edildiğinde

1. tür bildirimleri ve uygulamaları aynı üstbilgi dosyasında bulunan bir kitaplıkta

> [!NOTE]
> Geçerli sürümde, kod açıklamaları şablonlarda veya bir şablon türü içeren herhangi bir şeye (örneğin, bir parametreyi şablon olarak alan bir işlev) işlenmez. Bu tür açıklamaları eklemek tanımsız davranışa neden olur.

Belge açıklamalarıyla bir. xml dosyası oluşturma hakkında daha fazla bilgi için aşağıdaki konulara bakın.

|Hakkında bilgi için|Bkz.|
|---------------------------|---------|
|Kullanılacak derleyici seçenekleri|[/Doc](doc-process-documentation-comments-c-cpp.md)|
|Belgelerde yaygın olarak kullanılan işlevselliği sağlamak için kullanabileceğiniz Etiketler|[Belge açıklamaları için önerilen Etiketler](recommended-tags-for-documentation-comments-visual-cpp.md)|
|Kodunuzda yapıları tanımlamak için derleyicinin ürettiği KIMLIK dizeleri|[. Xml dosyası işleniyor](dot-xml-file-processing.md)|
|Belge etiketlerini sınırlandıran|[Visual C++ Belge Etiketleri için Sınırlayıcılar](delimiters-for-visual-cpp-documentation-tags.md)|
|Bir veya daha fazla. xdc dosyasından bir. xml dosyası oluşturuluyor.|[XDCMake başvurusu](xdcmake-reference.md)|
|Visual Studio Özellik alanlarıyla ilgili olarak XML hakkında bilgi bağlantıları|[Visual Studio 'da XML](/visualstudio/xml-tools/xml-tools-in-visual-studio)|

Bir belge açıklamasının metnine XML özel karakterleri yerleştirmeniz gerekiyorsa, XML varlıkları veya CDATA bölümü kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../../extensions/component-extensions-for-runtime-platforms.md)

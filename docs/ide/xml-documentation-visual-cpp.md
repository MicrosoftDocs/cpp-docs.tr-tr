---
title: XML belgeleri (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17853a43d3a94be779b659b0da825467fa66f61c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="xml-documentation-visual-c"></a>XML Belgeleri (Visual C++)
Visual C++'da, bir .xml dosyasına nasıl işleneceğini kaynak kodunuzu yorumlar ekleyebilirsiniz. Bu dosya daha sonra kodunuzda sınıfları için belgeleri oluşturan bir işlem girdisi olabilir.  
  
 Visual C++ kod dosyasında XML belgeleri yorumları doğrudan metot veya tür tanımı önce bulunduğu olması gerekir. Açıklamalar, aşağıdaki senaryolarda IntelliSense Quıckınfo veri ipucu doldurmak için kullanılabilir:  
  
1.  kodu içeren bir eşlik eden .winmd dosyası bir Windows çalışma zamanı bileşeni olarak ne zaman derlenir  
  
2.  Kaynak kodu geçerli projeye zaman dahil  
  
3.  bir Kitaplığı'nda, tür bildirimleri ve uygulamaları aynı üstbilgi dosyasında bulunur.  
  
> [!NOTE]
>  Geçerli sürümde, kod açıklamaları şablonları veya bir şablon türü (örneğin, bir şablon olarak bir parametre alan bir işlev) içeren herhangi bir şey işlenmez. Böyle açıklama ekleme tanımsız davranışlara neden.  
  
 Belge açıklamaları bir .xml dosyası oluşturma hakkında daha fazla bilgi için aşağıdaki konulara bakın.  
  
|Hakkında bilgi için|Bkz. |  
|---------------------------|---------|  
|Kullanılacak derleyici seçenekleri|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Yaygın olarak sağlamak için kullanabileceğiniz etiketleri işlevselliği belgelerde kullanılan|[Belge Açıklamaları için Önerilen Etiketler](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|Kodunuzda yapıları tanımlamak için derleyici üreten kimlik dizeleri|[.Xml dosyası işleme](../ide/dot-xml-file-processing.md)|  
|Belge etiketleri sınırlandırmak nasıl|[Visual C++ Belge Etiketleri için Sınırlayıcılar](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Bir veya daha fazla .xdc dosyalarından bir .xml dosyası oluşturuluyor.|[XDCMake Başvurusu](../ide/xdcmake-reference.md)|  
|Visual Studio özellik alanlarına şekliyle XML hakkında bilgilere bağlantılar ilişkilendirir|[Visual Studio'da XML](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 XML özel karakterleri belgelere açıklama metninde put gerekiyorsa, XML varlıkları veya CDATA bölümünde kullanmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)
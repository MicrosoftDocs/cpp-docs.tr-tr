---
title: "Belge açıklamaları (Visual C++) için önerilen etiketler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65d2161edc4b2aa03cd547467ca0f38158850051
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>Belge Açıklamaları için Önerilen Etiketler (Visual C++)
Visual C++ Derleyici, kodundaki belge açıklamaları işler ve her derlenecek dosya için bir .xdc dosyası oluşturur ve xdcmake.exe bir .xml dosyasına .xdc dosyaları işler. Belgeleri oluşturmak için .xml dosyası işleme sitenizde uygulanması gereken bir ayrıntı yoktur.  
  
 Etiketleri yapıları türleri gibi işlenir ve üyeleri yazın.  
  
 Etiketler hemen türler veya üyeler gelmelidir.  
  
> [!NOTE]
>  Belge açıklamaları özellikleri ve olayları için satır tanımı dışında bir ad alanı veya üzerinde uygulanamıyor; Belge açıklamaları sınıf bildirimlerinde gerekir.  
  
 Derleyici geçerli XML herhangi bir etiket işler. Aşağıdaki kullanıcı belgeleri yaygın olarak kullanılan işlevler sağlar:  
  
||||  
|-|-|-|  
|[\<c >](../ide/c-visual-cpp.md)|[\<kodu >](../ide/code-visual-cpp.md)|[\<Örnek >](../ide/example-visual-cpp.md)|  
|[\<Özel Durum >](../ide/exception-visual-cpp.md)1|[\<dahil >](../ide/include-visual-cpp.md)1|[\<Liste >](../ide/list-visual-cpp.md)|  
|[\<para >](../ide/para-visual-cpp.md)|[\<param >](../ide/param-visual-cpp.md)1|[\<paramref >](../ide/paramref-visual-cpp.md)1|  
|[\<izni >](../ide/permission-visual-cpp.md)1|[\<Açıklamalar >](../ide/remarks-visual-cpp.md)|[\<döndürür >](../ide/returns-visual-cpp.md)|  
|[\<bkz: >](../ide/see-visual-cpp.md)1|[\<SeeAlso >](../ide/seealso-visual-cpp.md)1|[\<Özet >](../ide/summary-visual-cpp.md)|  
|[\<Değer >](../ide/value-visual-cpp.md)|||  
  
 1. Derleyici sözdizimi doğrular.  
  
 Geçerli sürümde, Visual C++ derleyicisi desteklemediği `<paramref>`, diğer Visual Studio derleyicileri tarafından desteklenen bir etiket. Visual C++ destekleyebilir `<paramref>` gelecek bir sürümde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belgeleri](../ide/xml-documentation-visual-cpp.md)
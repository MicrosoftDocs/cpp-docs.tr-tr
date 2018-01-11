---
title: "Çeviri aşamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- translation phases
- preprocessor, translation
- translation, compiler process
- preprocessor
- file translation [C++], compiler process
- files [C++], translation
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22d73156d4f03a32bd9aa382dd0cc610f8a5f03f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="phases-of-translation"></a>Çeviri Aşamaları
C ve C++ programlarında her biri bazı program metin içeren bir veya daha fazla kaynak dosyaları oluşur. INCLUDE dosyalarından birlikte bir kaynak dosyası (kullanarak dahil olan dosyaları `#include` önişlemci yönergesi), ancak koşullu derleme yönergeleri tarafından gibi kaldırılan kodun bölümlerini dahil değil `#if`, "çeviri birim." olarak adlandırılır  
  
 Kaynak dosyaları farklı zamanlarda çevrilmiş — aslında, yalnızca güncel dosyaları çevirmek için yaygın bir sorundur. Çevrilen çeviri birimleri ayrı nesne dosyaları ya da nesne kodu kitaplıkları işlenebilir. Bu ayrı, çevrilmiş çeviri birimleri yürütülebilir bir program veya bir dinamik bağlantı kitaplığı (DLL) form bağlanır.  Bağlayıcı girişi olarak kullanılan dosyaları hakkında daha fazla bilgi için bkz: [LINK giriş dosyaları](../build/reference/link-input-files.md).  
  
 Çeviri birimleri kullanarak iletişim kurabilir:  
  
-   Dış bağlantı olan işlevler çağrıları.  
  
-   Dış bağlantı sınıf üyesi işlevleri çağrıları.  
  
-   Dış bağlantı nesneleri doğrudan değiştirilmesine.  
  
-   Dosyaları doğrudan değiştirilmesine.  
  
-   İşlemler arası iletişim (Microsoft Windows tabanlı uygulamalar için yalnızca).  
  
 Aşağıdaki listede derleyici dosyalarını çevirir aşamaları açıklanmaktadır:  
  
 *Karakter Eşleme*  
 Kaynak dosyanın karakter iç kaynak gösterimine eşlenir. Trigrafı dizileri tek karakterli iç gösterimi bu aşamasında dönüştürülür.  
  
 *Satır boşluklarına ayıran*  
 Bir ters eğik çizgiyi bitiş tüm satırları (**\\**) ve hemen ardından tarafından yeni satır karakteri fiziksel satırlarından mantıksal satırları oluşturan kaynak dosyasında sonraki satıra ile birleştirilir. Boş olmadığı sürece, bir kaynak dosya bir eğik öncesinde yeni satır karakteri bitmelidir.  
  
 *Simgeleştirme*  
 Kaynak dosya önişlem belirteçleri ve boşluk karakterleri ayrılır. Kaynak dosya yorumlar bir boşluk karakteri ile her değiştirilir. Satırbaşı karakterlerini korunur.  
  
 *Ön işleme*  
 Önişleme yönergeleri yürütülür ve makrolar kaynak dosyasına genişletilir. `#include` Deyimi dahil herhangi bir metin önceki üç çeviri adımları başlayarak çeviri çağırır.  
  
 *Karakter kümesi eşleme*  
 Tüm kaynak karakter kümesi üyeleri ve çıkış sıraları eşdeğerlerine yürütme karakter kümesi dönüştürülür. Microsoft C ve C++, hem kaynak hem de yürütme karakter kümesi ASCII içindir.  
  
 *Dize birleştirme*  
 Tüm bitişik dize ve geniş dize değişmez değerleri birleşir. Örneğin, `"String " "concatenation"` hale `"String concatenation"`.  
  
 *Çeviri*  
 Tüm belirteçleri sözdizimsel olarak ve anlam olarak analiz edilir; Bu belirteçler nesne koda dönüştürülür.  
  
 *Bağlantı*  
 Tüm dış başvuruları yürütülebilir bir program veya bir dinamik bağlantı kitaplığı oluşturmak çözümlenir.  
  
 Derleyici sözdizimi hataları bulduğu çeviri aşamaları sırasında uyarı veya hata verir.  
  
 Bağlayıcı tüm dış başvuruları çözümler ve bir araya getirerek bir yürütülebilir program ya da DLL oluşturur veya daha fazla çeviri birimleri standart kitaplıkları ile birlikte ayrı ayrı işlenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön İşlemci](../preprocessor/preprocessor.md)
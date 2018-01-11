---
title: "-GENPROFILE, - FASTGENPROFILE (Araçlı derleme Profil Oluştur) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 028b31044d035def628785969a04c27af4699f65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/ GENPROFILE, /FASTGENPROFILE (Araçlı derleme Profil Oluştur)
Profil temelli iyileştirme (PGO) desteklemek için bağlayıcı tarafından bir .pgd dosyasının üretilmesi belirtir.  / GENPROFILE ve /FASTGENPROFILE farklı varsayılan parametrelerini kullanın. Profil oluşturma sırasında duyarlık hızı ve bellek kullanımı ayrıcalık tanıma için /GENPROFILE kullanın. Daha küçük bellek kullanımı ve hız duyarlık ayrıcalık tanıma için /FASTGENPROFILE kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/{GENPROFILE|FASTGENPROFILE}[:{COUNTER32|COUNTER64|EXACT|MEMMAX=#|MEMMIN=#|NOEXACT|NOPATH|NOTRACKEH|PATH|PGD=filename|TRACKEH}]   
```  
  
## <a name="remarks"></a>Açıklamalar  
 COUNTER32 &#124; COUNTER64  
 COUNTER32 32-bit araştırma sayaçları ve 64-bit araştırma sayaçları belirtmek için COUNTER64 kullanımını belirtmek için kullanın. /GENPROFILE belirttiğinizde, COUNTER64 varsayılandır. /FASTGENPROFILE belirttiğinizde, COUNTER32 varsayılandır.  
  
 TAM &#124; NOEXACT  
 Tam Araştırmalar için iş parçacığı ınterlocked artışlarla belirtmek için kullanın. NOEXACT araştırmalar korumasız artışı işlemlerinde belirtir. NOEXACT varsayılandır.  
  
 MEMMAX değeri, MEMMIN = value =  
 MEMMAX ve MEMMIN bellekte eğitim verileri için maksimum ve minimum ayırma boyutunu belirlemek için kullanın. Bayt cinsinden ayrılan bellek miktarını değerdir.  Varsayılan olarak, bu değerleri bir iç buluşsal yöntem tarafından belirlenir.  
  
 YOL &#124; NOPATH  
 YOL PGO sayaçları her benzersiz yolu bir işlev için ayrı bir dizi belirtmek için kullanın. NOPATH sayaç her işlevi için yalnızca bir kümesini belirtmek için kullanın.   /GENPROFILE belirttiğinizde, bu varsayılan yoldur. /FASTGENPROFILE belirttiğinizde, NOPATH varsayılandır.  
  
 TRACKEH &#124; NOTRACKEH  
 Eğitim sırasında özel durumlar sırasında doğru sayısı tutmak için fazladan sayaçlar kullanılıp kullanılmayacağını belirtir. TRACKEH bir tam sayı için fazladan sayaçlar belirtmek için kullanın. Özel durum işleme kullanmıyorsa veya eğitim senaryolarınızı durumlar karşılaştığınız değil kodu için tek sayaçları belirtmek için NOTRACKEH kullanın.  /GENPROFILE belirttiğinizde, TRACKEH varsayılandır. /FASTGENPROFILE belirttiğinizde, NOTRACKEH varsayılandır.  
  
 PGD dosya adı =  
 .Pgd dosyası için bir temel dosya adı belirtir. Varsayılan olarak, bağlayıcı .pgd uzantısı ile temel yürütülebilir görüntü dosya adını kullanır.  
  
 /GENPROFILE ve /FASTGENPROFILE seçenekleri uygulama eğitim profil temelli iyileştirme için (PGO) desteklemek için gereken profil oluşturma araçları dosyası oluşturmak için bağlayıcı söyleyin. Uygulama eğitim tarafından oluşturulan profil bilgilerini gerçekleştirmek için giriş sırasında derlemeleri bütün program iyileştirmeleri hedeflenen olarak kullanılır.   Derlemeler ve uygulama eğitim sırasında performansı için çeşitli profil özelliklerini denetlemek için ek seçenekler ayarlayabilirsiniz. /GENPROFILE tarafından belirtilen varsayılan seçenekler özellikle büyük ve karmaşık çok iş parçacıklı uygulamalar için en doğru sonuçlar verir. /FASTGENPROFILE seçenek, düşük bellek alanını ve doğruluk ödün verme pahasına eğitim sırasında daha hızlı performans farklı Varsayılanları kullanır.  
  
 /FASTGENPROFILE /GENPROFILE kullanarak yapı sonra Araçlı uygulamayı çalıştırdığınızda, profil bilgileri yakalanır. /USEPROFILE seçeneği belirttiğinizde, bu bilgileri bağlayıcı tarafından kullanılır. Profil temelli iyileştirme, uygulamanızı eğitmek hakkında daha fazla bilgi ve toplanan veriler hakkında ayrıntılar için bkz.  
  
 /GENPROFILE veya /FASTGENPROFILE belirttiğinizde /LTCG belirtmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [/ LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)
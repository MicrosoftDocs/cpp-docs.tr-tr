---
title: "Derleyici iç bilgileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20b1416eacc6fa31c5e41b4a0539ce9ccbd99f88
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="compiler-intrinsics"></a>Derleyici İç Bilgileri
Çoğu işlevleri kitaplıklarında yer alır, ancak bazı işlevler yerleşiktir (diğer bir deyişle, iç) derleyici. Bunlar, iç işlevler veya iç bilgileri olarak adlandırılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işlev bir iç ise, bu işlev bir işlev çağrısı yükünden kurtularak ve bu işlev için yayınlaması için son derece verimli makine yönergeleri vererek genellikle eklenen satır içi kodudur. Bazı iyileştirmeler kullanılabilir şekilde iyileştirici kaç iç bilgileri davranır, bir yerleşik bilgisi olduğundan bir iç genellikle eşdeğer satır içi derleme hızlıdır olmayan kullanılabilir satır içi derleme kullanıldığında. Ayrıca, iyileştirici iç farklı genişletin, arabellek farklı şekilde hizalayın veya bağlam ve bağımsız değişkenler çağrının bağlı olarak diğer ayarlamalar yapın.  
  
 Visual C++'da kullanılabilir iç bilgileri ile diğer derleyiciler derlenmiş kod ve bazı hedef mimari için kullanılabilir bazı iç bilgileri kullanılabilir değilse kullanılamaz durumda olabilir çünkü iç bilgileri kullanımını kodu taşınabilirlik etkiler. Tüm mimari için. Ancak, iç bilgileri genellikle satır içi derleme daha fazla taşınabilir. İç bilgiler nerede satır içi derleme desteklenmiyor 64-bit mimariyi üzerinde gereklidir.  
  
 Bazı iç bilgileri gibi `__assume` ve `__ReadWriteBarrier`, iyileştirici davranışını etkileyen derleyici bilgileri sağlayın.  
  
 Bazı iç bilgileri yalnızca iç bilgileri kullanılabilir ve bazı hem işlevi ve iç uygulamaları kullanılabilir. Derleyicinin yalnızca belirli işlevleri etkinleştirmek istediğinize bağlı olarak iki yoldan biriyle iç uygulama kullanmasını söyleyebilirsiniz veya tüm iç bilgileri etkinleştirmek istiyor. İlk yol kullanmaktır `#pragma intrinsic(` *iç-işlevi-adı-liste*`)`. Pragma tek bir iç veya virgülle ayırarak birden çok iç bilgileri belirtmek için kullanılabilir. İkinci kullanmaktır [/Oi (iç işlevler Oluştur)](../build/reference/oi-generate-intrinsic-functions.md) tüm iç bilgileri belirli bir platformda kullanılabilir hale getirir derleyici seçeneği. Altında **/Oi**, kullanın `#pragma function(` *iç-işlevi-adı-liste* `)` bir iç yerine kullanılacak bir işlev çağrısı zorlamak için. Belirli bir iç belgelerine notlar, yordam yalnızca bir iç kullanılabilir, sonra iç uygulama olup olmamasına bakılmaksızın kullanılan **/Oi** veya `#pragma intrinsic` belirtilir. Tüm durumlarda **/Oi** veya `#pragma intrinsic` sağlar, ancak zorlama, iç kullanmak için en iyi hale getirme. İyileştirici hala işlevi çağırabilirsiniz.  
  
 Bazı standart C/C++ Kitaplık işlevleri bazı mimarileri iç uygulamalarında kullanılabilir. CRT işlevi çağrılırken iç uygulama kullanılır **/Oi** komut satırında belirtilen.  
  
 Üstbilgi dosyası \<intrin.h >, olan ortak iç işlevler için prototipleri bildiren kullanılabilir. Üreticiye özel yapı kullanılabilir \<immintrin.h > ve \<ammintrin.h > üst bilgi dosyaları. Ayrıca, belirli Windows üstbilgileri iç derleyici bir harita işlevleri bildirin.  
  
 Aşağıdaki bölümlerde üzerinde çeşitli mimarileri kullanılabilir tüm iç bilgi listesi. İç bilgiler belirli hedef işlemcinizin nasıl çalıştığını daha fazla bilgi için üreticinin başvuru belgelerine bakın.  
  
-   [ARM İç Bilgileri](../intrinsics/arm-intrinsics.md)  
  
-   [x86 İç Bilgi Listesi](../intrinsics/x86-intrinsics-list.md)  
  
-   [x64 (amd64) İç Bilgi Listesi](../intrinsics/x64-amd64-intrinsics-list.md)  
  
-   [Tüm Mimarilerde Kullanılabilen İç Bilgiler](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [İç İşlevlerin Alfabetik Listesi](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ARM Assembler başvurusu](../assembler/arm/arm-assembler-reference.md)   
 [Microsoft Macro Assembler başvurusu](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)
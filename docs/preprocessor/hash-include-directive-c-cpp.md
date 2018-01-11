---
title: "#<a name=\"include-directive-cc--microsoft-docs\"></a>include yönergesi (C/C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#include'
dev_langs: C++
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f724d566703300d0f929df680b659b7adbfa9577
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="include-directive-cc"></a>#include Yönergesi (C/C++)
Kaynak programda yönergesi göründüğü noktada göründükleri gibi belirtilen bir dosyanın içeriğini işlemek için önişlemci söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      #include  "path-spec"  
#include  <path-spec>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 INCLUDE dosyalarına sabiti ve makrosu tanımlarını düzenleyebilir ve ardından `#include` yönergeleri herhangi bir kaynak dosyaya ekleyin. Dahil dosyaları dış değişkenleri ve karmaşık veri türlerini bildirimlerini ekleme için yararlı de. Türleri tanımlanır ve bu amaçla oluşturulmuş bir içerme dosyası yalnızca bir kez adlı.  
  
 `path-spec` Dizin belirtimine göre isteğe bağlı olarak öncesinde bir dosya adı değil. Dosya adı, varolan bir dosyanın adı olmalıdır. Söz dizimi `path-spec` program derlenmiş işletim sistemine bağlıdır.  
  
 Kullanarak derlenmiş bir C++ uygulaması derlemelerde başvuru hakkında bilgi için [/CLR](../build/reference/clr-common-language-runtime-compilation.md), bkz: [#using](../preprocessor/hash-using-directive-cpp.md).  
  
 Her iki sözdizimi tüm içeriğini belirtilen içerme dosyası tarafından değiştirilmesi bu yönergesi neden. Yolun eksik olarak belirtildiğinde, önişlemci üstbilgi dosyaları için arama sırasını iki form arasındaki farktır. Aşağıdaki tabloda iki sözdizimi arasındaki farkı gösterir.  
  
|Sözdizimi formu|Eylem|  
|-----------------|------------|  
|Tırnak işaretli formu|Bu sırada dosyaları Ekle önişlemci arar:<br /><br /> 1) aynı dizinde içeren dosyayı `#include` deyimi.<br /><br /> 2) dizinler açık durumdaki, açıldıkları ters sırada dosyaları içerir. Üst dizininde arama başlar dosya ekleyin ve aracılığıyla yukarı doğru devam herhangi iki üst dizinleri dosyaları içerir.<br /><br /> 3) her /ı derleyici seçeneği tarafından belirtilen yola.<br /><br /> 4)<br /><br /> INCLUDE ortam değişkeni tarafından belirtilen yol.|  
|Açılı ayraç formu|Bu sırada dosyaları Ekle önişlemci arar:<br /><br /> 1) her /ı derleyici seçeneği tarafından belirtilen yol boyunca.<br /><br /> 2) ne zaman INCLUDE ortam değişkeni tarafından belirtilen yol boyunca komut satırında derleme oluşur.|  
  
 Verilen ada sahip bir dosyayı bulur hemen arama önişlemci durdurur. Çift tırnak işaretleri arasında içerme dosyası için bir tam ve anlaşılır yolu belirtimi içine varsa (""), önişlemci yalnızca o yol belirtimi arar ve standart dizinleri yok sayar.  
  
 Çift tırnak içine alınmış dosya adı bir tam yol belirtimi ise, "üst" dosyasının dizin önişlemci ilk arar. Üst dosya içeren bir dosyadır `#include` yönergesi. Örneğin, adında bir dosya içeriyorsa `file2` adlı bir dosyaya `file1`, `file1` üst dosyasıdır.  
  
 "İç içe olabilir"; dosyaları dahil etme diğer bir deyişle, bir `#include` yönergesi başkası tarafından adlı bir dosyada görünebilir `#include` yönergesi. Örneğin, `file2` içerebilir `file3`. Bu durumda, `file1` üst hala olacaktır `file2`, ancak bu, "iki"üst olacaktır `file3`.  
  
 Ne zaman dahil dosyaları iç içe geçmiş ve komut satırında derleme ortaya çıktığında, dizin arama üst dosya dizinleri ile başlar ve iki üst dosyalarla dizinleri ile devam eder. Diğer bir deyişle, aramaya işlenmekte olan kaynak içeren dizine göre başlar. Dosya bulunamazsa, arama /ı derleyici seçeneği tarafından belirtilen dizin taşır. Son olarak, INCLUDE ortam değişkeni tarafından belirtilen dizin aranır.  
  
 Geliştirme ortamından INCLUDE ortam değişkeni göz ardı edilir. İçin dosyaları Ekle aranır dizinleri ayarlama hakkında bilgi — bu LIB ortam değişkeni için de geçerlidir; bkz [VC ++ dizinleri özellik sayfası](../ide/vcpp-directories-property-page.md).  
  
 Bu örnek, köşeli parantez kullanarak dosya ekleme gösterir:  
  
```  
#include <stdio.h>  
```  
  
 Bu örnek STDIO adlı dosyanın içeriğini ekler. Kaynak program H. Köşeli STDIO için Include ortam değişkeni tarafından belirtilen dizin aramak önişlemci neden. /I derleyici seçeneği tarafından belirtilen dizinleri arar sonra H.  
  
 Sonraki örnek tırnak işaretli formunu kullanarak dosya ekleme gösterir:  
  
```  
#include "defs.h"  
```  
  
 Bu örnek DEFS tarafından belirtilen dosyanın içeriğini ekler. Kaynak program H. Tırnak işaretleri önişlemci önce üst kaynak dosyasını içeren dizine arar anlamına gelir.  
  
 Dosyaları Ekle iç içe geçmiş en fazla 10 düzeyleri devam edebilirsiniz. Zaman iç içe `#include` olan işlenen, önişlemci kapsayan içerme dosyası özgün kaynak dosyasına eklemek devam eder.  
  
 **Microsoft özel**  
  
 İncludable kaynak dosyalarını bulmak için /ı derleyici seçeneği tarafından belirtilen dizinleri önişlemci ilk arar. Önişlemci INCLUDE ortam değişkeni /ı seçeneği mevcut değil veya başarısız olursa, köşeli parantez içinde içerme dosyaları bulmak için kullanır. INCLUDE ortam değişkeni ve /ı derleyici seçeneği noktalı virgülle (;) ayırarak birden fazla yol içerebilir. Birden fazla dizine parçası olarak /ı seçeneği veya INCLUDE ortam değişkeni içinde görünüyorsa, önişlemci bunları göründükleri sırada arar.  
  
 Örneğin, komut  
  
```  
CL /ID:\MSVC\INCLUDE MYPROG.C  
```  
  
 STDIO gibi içerme dosyaları D:\MSVC\INCLUDE\ dizinde aramak önişlemci neden olur. H. Komutları  
  
```  
SET INCLUDE=D:\MSVC\INCLUDE  
CL MYPROG.C  
```  
  
 aynı etkiye sahiptir. İki aramaları başarısız olursa, önemli derleyici hatası oluşur.  
  
 Dosya adı tam olarak bir içerme dosyası için bir yol olan belirtilirse, iki nokta üst üste (örneğin, F:\MSVC\SPECIAL\INCL\TEST. içerir H) önişlemci yolunu izler.  
  
 Olarak belirtilen içerme dosyaları için `#include` "`path-spec`", dizin arama üst dosyasının dizin ile başlar ve iki üst dosyalarla dizinleri ile devam eder. Diğer bir deyişle, aramaya içeren kaynak dosyasını içeren dizine göre başlar `#include` işleniyor yönergesi. Dosya adı açılı ayraç gibi iki üst varlık dosyası yok ve dosya bulunamadı, aramaya devam eder.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)
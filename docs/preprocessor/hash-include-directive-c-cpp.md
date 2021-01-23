---
description: 'Daha fazla bilgi edinin: #include yönergesi (C/C++)'
title: '##include yönergesi (C/C++)'
ms.date: 01/19/2021
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.openlocfilehash: 4ba9b07b77d919e8587fc392518d268b935e0c46
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713629"
---
# <a name="include-directive-cc"></a>`#include` yönergesi (C/C++)

Önişlemcinin belirtilen bir dosyanın içeriğini yönergenin göründüğü noktada içermesini söyler.

## <a name="syntax"></a>Syntax

> **`#include "`***yol-spec***`"`**\
> **`#include <`***yol-spec***`>`**

## <a name="remarks"></a>Açıklamalar

Sabit ve Makro tanımlarını *içerme dosyaları* ( *başlık dosyaları* olarak da bilinir) halinde düzenleyebilir ve ardından **`#include`** bunları herhangi bir kaynak dosyaya eklemek için yönergeleri kullanabilirsiniz. İçerme dosyaları, dış değişkenlerin bildirimleri ve karmaşık veri türleri dahil etmek için de kullanışlıdır. Türler, bu amaçla oluşturulan bir içerme dosyasında tanımlanmış ve yalnızca bir kez adlandırılmış olabilir.

*Path-spec* , isteğe bağlı olarak önceden bir dizin belirtimi olabilecek bir dosya adıdır. Dosya adı var olan bir dosyayı adı olmalıdır. *Path-spec* sözdizimi, programın derlendiği işletim sistemine bağlıdır.

Kullanılarak derlenen bir C++ uygulamasındaki derlemelere nasıl başvurulacağını hakkında bilgi için [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) , bkz. [ `#using` yönergesi](../preprocessor/hash-using-directive-cpp.md).

Her iki sözdizimi biçimi de **`#include`** yönergenin belirtilen dosyanın tüm içeriğiyle değiştirilmesine neden olur. İki form arasındaki fark, yol tam olarak belirtilmediğinde Önişlemci 'nin aradığı yolların sıralarıdır. Aşağıdaki tablo, iki sözdizimi formu arasındaki farkı gösterir.

| Söz dizimi biçimi | Eylem |
|--|--|
| Alıntılanmış form | Önişlemci, içerme dosyalarını şu sırayla arar:<br/><br/> 1) deyimin bulunduğu dosya ile aynı dizinde **`#include`** .<br/><br/> 2) Şu anda açılan içerme dosyalarının dizinlerinde, açıldıkları ters sırada. Arama, üst öğe ekleme dosyası dizininde başlar ve herhangi bir doğru üst öğe içerme dosyasının dizinleriyle devam eder.<br/><br/> 3) her derleyici seçeneği tarafından belirtilen yol üzerinde **`/I`** .<br/><br/> 4) ortam değişkeni tarafından belirtilen yollar üzerinde `INCLUDE` . |
| Açılı ayraç formu | Önişlemci, içerme dosyalarını şu sırayla arar:<br/><br/> 1) her derleyici seçeneği tarafından belirtilen yol üzerinde **`/I`** .<br/><br/> 2) komut satırında derleme yapıldığında, ortam değişkeni tarafından belirtilen yollar gösterilir `INCLUDE` . |

Önişlemci, belirtilen ada sahip bir dosya bulduğu anda aramayı durduruyor. Çift tırnak işaretleri () arasında ekleme dosyası için tamamen, belirsiz bir yol belirtimi eklerseniz `" "` , Önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

Çift tırnak işareti içine alınmış dosya adı bir eksik yol belirtimidir, önişlemci önce *üst* dosyanın dizinini arar. Ana dosya, yönergesini içeren dosyadır **`#include`** . Örneğin, *FILE1* adlı bir dosyaya *dosya2* adlı bir dosya eklerseniz, *FILE1* üst dosyadır.

İçerme dosyaları *iç içe* olabilir: bir **`#include`** yönerge, başka bir yönergeyle adlandırılan dosyada görünebilir **`#include`** . Örneğin, *dosya2* , *File3* içerebilir. Bu durumda *FILE1* , *dosya2*'in üst öğesi olmaya devam eder, ancak *File3* öğesinin üst öğesi olacaktır.

Dahil etme dosyaları iç içe olduğunda ve komut satırında derleme gerçekleştiğinde, Dizin arama ana dosyanın dizininde başlar. Ardından, herhangi bir alt üst dosyanın dizinlerinde ilerler. Diğer bir deyişle, arama, işlenmekte olan kaynağı içeren dizine göre başlar. Dosya bulunamazsa, arama [ `/I` (ek dizinler dahil)](../build/reference/i-additional-include-directories.md) derleyici seçeneği tarafından belirtilen dizinlere gider. Son olarak, ortam değişkeni tarafından belirtilen dizinler `INCLUDE` aranır.

Visual Studio geliştirme ortamı içinde, `INCLUDE` ortam değişkeni yok sayılır. Bunun yerine, içerme dizinleri için proje özelliklerinde belirtilen değerler kullanılır. Visual Studio 'da içerme dizinlerini ayarlama hakkında daha fazla bilgi için bkz. [dizinleri](../build/reference/vcpp-directories-property-page.md#directory-types) ve [ek içerme dizinlerini](../build/reference/c-cpp-prop-page.md#additional-include-directories)ekleme.

Bu örnek, açılı ayraçlar kullanarak dosya eklemeyi gösterir:

```C
#include <stdio.h>
```

Örnek, adlı dosyanın içeriğini *`stdio.h`* kaynak programa ekler. Açılı ayraçlar, Önişlemci 'nin, `INCLUDE` *`stdio.h`* derleyici seçeneği tarafından belirtilen dizinleri aradıktan sonra, için ortam değişkeni tarafından belirtilen dizinlerde arama yapılmasına neden olur **`/I`** .

Sonraki örnekte, tırnak içine alınmış biçimi kullanarak dosya ekleme gösterilmektedir:

```C
#include "defs.h"
```

Örnek, tarafından belirtilen dosyanın içeriğini *`defs.h`* kaynak programa ekler. Tırnak işaretleri, önişlemcinin ilk önce üst kaynak dosyayı içeren dizini arayacağı anlamına gelir.

Ekleme dosyalarının iç içe geçirilmesi 10 düzeye kadar devam edebilir. İç içe işlem **`#include`** tamamlandığında, Önişlemci kapsayan üst öğe ekleme dosyasını özgün kaynak dosyasına eklemeye devam eder.

**Microsoft'a özgü**

Dahil edilecek kaynak dosyalarını bulmak için önişlemci ilk olarak derleyici seçeneği tarafından belirtilen dizinleri arar **`/I`** . **`/I`** Seçenek yoksa veya başarısız olursa Önişlemci, `INCLUDE` açılı ayraçlar içinde herhangi bir içerme dosyasını bulmak için ortam değişkenini kullanır. `INCLUDE`Ortam değişkeni ve **`/I`** derleyici seçeneği, noktalı virgülle () ayırarak birden çok yol içerebilir **`;`** . Seçeneğin bir parçası olarak birden fazla dizin görünüyorsa **`/I`** veya `INCLUDE` ortam değişkeni içinde, Önişlemci bunları göründükleri sırada arar.

Örneğin, komut

```cmd
CL /ID:\msvc\include myprog.c
```

önişlemcinin, gibi ekleme dosyaları için dizinde arama yapmasına neden olur *`D:\msvc\include\`* *`stdio.h`* . Komutlar

```cmd
SET INCLUDE=D:\msvc\include
CL myprog.c
```

aynı etkiye sahiptir. Her iki arama kümesi de başarısız olursa, önemli bir derleyici hatası oluşturulur.

Dosya adı iki nokta (örneğin,) içeren bir yol içeren bir içerme dosyası için tam olarak belirtilmişse *`F:\MSVC\SPECIAL\INCL\TEST.H`* , Önişlemci yolu izler.

Olarak belirtilen içerme dosyaları için `#include "path-spec"` Dizin arama, üst dosyanın dizininde başlar ve ardından herhangi bir alt üst dosyanın dizinlerine ilerler. Diğer bir deyişle, arama işlenen kaynak dosyayı içeren dizine göre başlar. Herhangi bir üst dosya yoksa ve dosya hala bulunamazsa arama, dosya adı açılı ayraçlar içine alınmış gibi devam eder.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[`/I` (Ek ekleme dizinleri)](../build/reference/i-additional-include-directories.md)

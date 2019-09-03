---
title: '##include yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
ms.openlocfilehash: 0792f522427e5658de992969745878894fbd454d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220254"
---
# <a name="include-directive-cc"></a>#include yönergesi (C/C++)

Önişlemci 'nin belirtilen bir dosyanın içeriğini, yönergenin göründüğü noktada kaynak programda görünmiş gibi vermesini söyler.

## <a name="syntax"></a>Sözdizimi

> **#include** "*Path-spec*" \
> **#include** *yol-spec* \<>

## <a name="remarks"></a>Açıklamalar

Sabit ve Makro tanımlarını içerme dosyaları halinde düzenleyebilir ve ardından bunları herhangi bir kaynak dosyasına eklemek için **#include** yönergelerini kullanabilirsiniz. İçerme dosyaları, dış değişkenlerin bildirimleri ve karmaşık veri türleri dahil etmek için de kullanışlıdır. Türler, bu amaçla oluşturulan bir içerme dosyasında tanımlanmış ve yalnızca bir kez adlandırılmış olabilir.

*Path-spec* , isteğe bağlı olarak önceden bir dizin belirtimi olabilecek bir dosya adıdır. Dosya adı var olan bir dosyayı adı olmalıdır. *Path-spec* sözdizimi, programın derlendiği işletim sistemine bağlıdır.

C++ [/Clr](../build/reference/clr-common-language-runtime-compilation.md)kullanılarak derlenen bir uygulamadaki derlemelere başvurma hakkında daha fazla bilgi için bkz. [#using](../preprocessor/hash-using-directive-cpp.md).

Her iki sözdizimi biçimi de bu yönergenin, belirtilen içerme dosyasının tüm içeriğiyle değiştirilmesine neden olur. İki form arasındaki fark, yol tam olarak belirtilmediğinde Önişlemci 'nin üst bilgi dosyalarını arayacağı sıradır. Aşağıdaki tablo, iki sözdizimi formu arasındaki farkı gösterir.

|Söz dizimi biçimi|Eylem|
|---|------------|
|Alıntılanmış form|Önişlemci, içerme dosyalarını şu sırayla arar:<br/><br/> 1) **#include** ifadesini içeren dosyayla aynı dizinde.<br/><br/> 2) Şu anda açılan içerme dosyalarının dizinlerinde, açıldıkları ters sırada. Arama, üst öğe ekleme dosyası dizininde başlar ve herhangi bir doğru üst öğe içerme dosyasının dizinleriyle devam eder.<br/><br/> 3) her **/ı** derleyici seçeneği tarafından belirtilen yol üzerinde.<br/><br/> 4), ıNCLUDE ortam değişkeni tarafından belirtilen yollar üzerinde.|
|Açılı ayraç formu|Önişlemci, içerme dosyalarını şu sırayla arar:<br/><br/> 1) her **/ı** derleyici seçeneği tarafından belirtilen yol üzerinde.<br/><br/> 2) komut satırında derleme yapıldığında, ıNCLUDE ortam değişkeni tarafından belirtilen yollar gösterilir.|

Önişlemci, belirtilen ada sahip bir dosya bulduğu anda aramayı durduruyor. Çift tırnak işaretleri (`" "`) arasında ekleme dosyası için tamamen, belirsiz bir yol belirtimi eklerseniz, Önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

Çift tırnak işareti içine alınmış dosya adı tamamlanmamış bir yol belirtimi ise, önişlemci önce "üst" dosyanın dizininde arama yapar. Bir üst dosya **#include** yönergesini içeren dosyadır. Örneğin, *FILE1*adlı bir dosyaya *dosya2* adlı bir dosya eklerseniz, *FILE1* üst dosyadır.

İçerme dosyaları "iç içe geçmiş" olabilir: **#İnclude** yönergesi, başka bir **#include** yönergesi tarafından adlandırılan dosyada görünebilir. Örneğin, *dosya2* , *File3*içerebilir. Bu durumda *FILE1* , *dosya2*'in üst öğesi olmaya devam eder, ancak bu, *File3*'in "bir üst öğesi" olacaktır.

Dahil etme dosyaları iç içe olduğunda ve komut satırında derleme gerçekleştiğinde, Dizin arama ana dosyanın dizinlerinde başlar. Ardından, herhangi bir alt üst dosyanın dizinlerinde ilerler. Diğer bir deyişle, arama, işlenmekte olan kaynağı içeren dizine göre başlar. Dosya bulunamazsa, arama [/ı (ek içerme dizinleri)](../build/reference/i-additional-include-directories.md) derleyici seçeneği tarafından belirtilen dizinlere gider. Son olarak, ıNCLUDE ortam değişkeni tarafından belirtilen dizinler aranır.

Visual Studio geliştirme ortamında, ıNCLUDE ortam değişkeni yok sayılır. İçerme dosyaları ve kitaplık dosyaları için aranan dizinleri ayarlama hakkında daha fazla bilgi için bkz. [VC + + dizinleri Özellik sayfası](../build/reference/vcpp-directories-property-page.md).

Bu örnek, açılı ayraçlar kullanarak dosya eklemeyi gösterir:

```C
#include <stdio.h>
```

Bu örnek, STDIO adlı dosyanın içeriğini ekler. Kaynak programa H. Açılı ayraçlar, Önişlemci 'nin STDIO için ıNCLUDE ortam değişkeni tarafından belirtilen dizinlerde arama yapılmasına neden olur. H, **/ı** derleyici seçeneği tarafından belirtilen dizinleri arar.

Sonraki örnekte, tırnak içine alınmış biçimi kullanarak dosya ekleme gösterilmektedir:

```C
#include "defs.h"
```

Bu örnek, DEFS tarafından belirtilen dosyanın içeriğini ekler. Kaynak programa H. Tırnak işaretleri, önişlemcinin ilk önce üst kaynak dosyayı içeren dizini arayacağı anlamına gelir.

Ekleme dosyalarının iç içe geçirilmesi 10 düzeye kadar devam edebilir. İç içe **#include** işlendiğinde, Önişlemci kapsayan içerme dosyasını özgün kaynak dosyasına eklemeye devam eder.

**Microsoft 'a özgü**

Dahil edilen kaynak dosyaları bulmak için önişlemci ilk olarak **/ı** derleyici seçeneği tarafından belirtilen dizinleri arar. **/I** seçeneği yoksa veya başarısız olursa, ön işlemci, köşeli parantez içinde herhangi bir içerme dosyasını bulmak için INCLUDE ortam değişkenini kullanır. INCLUDE ortam değişkeni ve **/ı** derleyici seçeneği, noktalı virgülle ( **;** ) ayırarak birden çok yol içerebilir. **/İ** seçeneğinin bir parçası olarak birden fazla dizin GÖRÜNÜRSE veya INCLUDE ortam değişkeni içinde, Önişlemci bunları göründükleri sırada arar.

Örneğin, komut

```cmd
CL /ID:\MSVC\INCLUDE MYPROG.C
```

Önişlemci 'nin D:\MSVC\INCLUDE\ dizinini STDIO gibi içerme dosyalarını aramasına neden olur. Olsun. Komutlar

```cmd
SET INCLUDE=D:\MSVC\INCLUDE
CL MYPROG.C
```

aynı etkiye sahiptir. Her iki arama kümesi de başarısız olursa, önemli bir derleyici hatası oluşturulur.

Dosya adı, iki nokta içeren bir yol içeren bir içerme dosyası için tam olarak belirtildiyse (örneğin, F:\MSVC\SPECIAL\INCL\TEST). H), Önişlemci yolu izler.

Olarak `#include "path-spec"`belirtilen içerme dosyaları için Dizin arama, üst dosyanın diziniyle başlar ve ardından herhangi bir alt üst dosyanın dizinlerine ilerler. Diğer bir deyişle, arama işlemi işlenen **#include** yönergesini içeren kaynak dosyayı içeren dizine göre başlar. Herhangi bir üst öğe dosyası yoksa ve dosya bulunmazsa arama, dosya adı açılı ayraçlar içine alınmış gibi devam eder.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)\
[/İ (ek ekleme dizinleri)](../build/reference/i-additional-include-directories.md)

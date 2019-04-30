---
title: '#INCLUDE yönergesi (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
ms.openlocfilehash: 7ffccb34d52f8ffa1e6b9cc64a58d3471d02ac92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388143"
---
# <a name="include-directive-cc"></a>#include Yönergesi (C/C++)

Belirtilen dosyanın içeriğini kaynak programda yönergenin göründüğü noktada gibi görünüyorlarsa değerlendirilecek önişlemci söyler.

## <a name="syntax"></a>Sözdizimi

```
#include  "path-spec"
#include  <path-spec>
```

## <a name="remarks"></a>Açıklamalar

Sabit ve makro tanımlarını içerme dosyaları halinde düzenleyin ve ardından **#include** bunları dilediğiniz kaynak dosyaya eklemek için yönergeleri. Dahil dosyalarıdır aynı zamanda dış değişkenlerin ve karmaşık veri türlerinin bildirimlerini birleştirmek için yararlıdır. Türleri tanımlanır ve bu amaç için oluşturulan ekleme dosyasında yalnızca bir kez adlı.

*Path-spec* isteğe bağlı olarak bir dizin belirtimi bulunabilen bir dosya adı. Dosya adı, var olan bir dosya adı olmalıdır. Söz dizimi *path-spec* programın derlendiği işletim sistemine bağlıdır.

Kullanarak derlenen bir C++ uygulamasındaki derlemelere başvurma hakkında bilgi için [/CLR](../build/reference/clr-common-language-runtime-compilation.md), bkz: [#using](../preprocessor/hash-using-directive-cpp.md).

Her iki sözdizimi biçimi, belirlenen içerme dosyasına içeriğin tümüne göre değiştirilmesi, bu yönergenin neden. İki biçim arasındaki fark, yol belirtilmediğinde önişlemcinin içinde önişlemcinin başlık dosyalarını arama sırasıdır. Aşağıdaki tabloda, iki sözdizimi formu arasındaki farkı gösterir.

|Söz dizimi biçimi|Eylem|
|---|------------|
|Tırnak işareti|Önişlemci ekleme dosyalarını şu sırayla arar:<br/><br/> (1) de içeren dosyasını aynı dizine **#include** deyimi.<br/><br/> (2) dizinler şu anda açılan, açıldıklarının tersi sıradadır dosyaları içerir. Arama üst dizininde başlar dosyasını dahil edin ve yukarı doğru devam ederek dosyaları herhangi iki üst dizinleri içerir.<br/><br/> 3) her tarafından belirtilen yol boyunca **/I** derleyici seçeneği.<br/><br/> 4) INCLUDE ortam değişkeni tarafından belirtilen yollarda.|
|Açılı ayraç biçimi|Önişlemci ekleme dosyalarını şu sırayla arar:<br/><br/> (1) her tarafından belirtilen yol boyunca **/I** derleyici seçeneği.<br/><br/> 2) yollarda derleme komut satırında gerçekleştiğinde, INCLUDE ortam değişkeni tarafından belirtilir.|

Belirtilen ada sahip bir dosya bulduktan hemen sonra aramayı önişlemci durdurur. Tam, Belirsiz olmayan bir yol belirtimi içerik dosyası için çift tırnak içine alırsanız (**""**), önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

Çift tırnak içine alınmışsa dosya adı bir eksik yol belirtimidir, önişlemci önce "üst" öğenin dizininde arama yapar. Ana dosya içeren dosyadır **#include** yönergesi. Örneğin, adında bir dosya eklerseniz *dosya2* adındaki bir dosyaya *fıle1'de*, *fıle1'de* üst dosyasıdır.

İçerme dosyaları "iç içe olabilir"; diğer bir deyişle, bir **#include** yönergesi bir başkası tarafından adlı bir dosyada görünebilir **#include** yönergesi. Örneğin, *dosya2* içerebilir *dosya3*. Bu durumda, *dosya1* , üst öğe olmaya *dosya2*, ancak "iki üst" olur *dosya3*.

Ne zaman dahil dosyaları iç içe ve komut satırında derleme gerçekleştiğinde, dizin arama ana dosyanın ile başlayıp ardından üst dosyaların dizinleriyle devam eder. Diğer bir deyişle, arama, işlenmekte olan kaynağı içeren dizine göre başlar. Dosya bulunamazsa arama tarafından belirtilen dizinlere taşır [/ı (ek içeren dizinler)](../build/reference/i-additional-include-directories.md) derleyici seçeneği. Son olarak, INCLUDE ortam değişkeni tarafından belirtilen dizinlerde arama yapılır.

Visual Studio geliştirme ortamından INCLUDE ortam değişkeni yoksayıldı. Dahil etme dosyaları için Aranan dizinleri ayarlama hakkında daha fazla bilgi için — bu ayrıca LIB ortamı değişkeni için geçerlidir — bkz [VC ++ Directories Property Page](../build/reference/vcpp-directories-property-page.md).

Bu örnek, açılı ayraçlar kullanarak dosya eklemeyi gösterir:

```
#include <stdio.h>
```

Bu örnek STDIO adlı dosyanın içeriklerini ekler. Kaynak program için H. Açılı ayraçlar önişlemcinin STDIO için Include ortam değişkeni tarafından belirtilen dizinlerini aramasına neden olur. Tarafından belirtilen dizinleri aradıktan sonra H **/I** derleyici seçeneği.

Sonraki örnek, tırnak işareti kullanarak dosya eklemeyi gösterir:

```
#include "defs.h"
```

Bu örnek DEFS tarafından belirtilen dosyanın içeriklerini ekler. Kaynak program için H. Tırnak işareti, önişlemcinin ilk üst kaynak dosyanın bulunduğu dizini araması anlamına gelir.

Dahil etme dosyaları iç içe geçmiş en fazla 10 düzeye kadar devam eder. İç içe **#include** olan işlendiğinde, önişlemci kapsayan içerik dosyasını orijinal kaynak dosyasına eklemeye devam eder.

**Microsoft'a özgü**

Dahil edilebilecek kaynak dosyalarını bulmak için önişlemci ilk tarafından belirtilen dizinleri arar **/I** derleyici seçeneği. Varsa **/I** seçeneği mevcut değil veya başarısız olursa, önişlemci INCLUDE ortam değişkeni köşeli ayraç içindeki içerik dosyalarını bulmak için kullanır. INCLUDE ortam değişkeni ve **/I** derleyici seçeneği noktalı virgülle ayırarak birden fazla yol içerebilir (**;**). Kapsamında birden fazla dizin görünüyorsa **/I** seçeneğini veya INCLUDE ortam değişkeni içinde önişlemci bunları göründükleri sırayla arar.

Örneğin, komut

```
CL /ID:\MSVC\INCLUDE MYPROG.C
```

önişlemcinin dizininde D:\MSVC\INCLUDE\ STDIO gibi dosyaları aramasına neden olur. H Komutları

```
SET INCLUDE=D:\MSVC\INCLUDE
CL MYPROG.C
```

aynı etkiye sahiptir. Her iki arama kümesi de başarısız olursa, önemli bir derleyici hatası oluşturulur.

Dosya adı tam olarak bir dahil etme dosyası için bir yol olan belirtildiyse, iki nokta üst üste (örneğin, F:\MSVC\SPECIAL\INCL\TEST. içerir. H), önişlemci yolu izler.

Olarak belirtilen dosyaları eklemek `#include "path-spec"`, dizin arama ana dosyanın başlar ve ardından üst dosyaların dizinleriyle devam eder. Diğer bir deyişle, arama içeren kaynak dosyayı içeren dizine göre başlar **#include** işleniyor yönergesi. Dosya adı köşeli ayraçlar içine alınan iki üst dosya yok ve dosyayı bulunamadı, arama gibi devam eder.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)<br/>
[/I (ek içeren dizinler)](../build/reference/i-additional-include-directories.md)<br/>

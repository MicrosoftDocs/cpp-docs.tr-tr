---
title: 2.7.2.6 reduction
ms.date: 11/04/2016
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
ms.openlocfilehash: 54b326feb4e4ccf1f1da5c8152ffc8d1e4bd13b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456023"
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

Bu yan tümce görünen skalar değişkenler bir azaltma gerçekleştirir *değişken listesi*, işleciyle *op*. Söz dizimi `reduction` yan tümcesi şu şekildedir:

> azaltma (*op*: *değişken listesi*)

Azaltma, genellikle aşağıdaki biçimlerden birini içeren bir ifade için belirtilir:

> *x* = *x* *op* *expr*
> *x* *binop* = *expr*
> *x* = *expr* *op* *x* (hariç çıkarma için) *x*++
> ++*x*
> *x*--
> --*x*

burada:

*x*<br/>
Belirtilen azaltma değişkenleri birini `list`.

*değişken listesi*<br/>
Skalar azalma değişkenlerin virgülle ayrılmış listesi.

*ifade*<br/>
Bir ifade başvurmuyor skalar türü ile *x*.

*OP*<br/>
Aşırı yüklenmiş bir işleç değil ancak biri, +, &#42;, -, &amp;, ^, &#124;, &amp; &amp;, veya &#124; &#124;.

*binop*<br/>
Aşırı yüklenmiş bir işleç değil ancak biri, +, &#42;, -, &amp;, ^, veya &#124;.

Aşağıdaki örneğidir `reduction` yan tümcesi:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Örnekte gösterildiği gibi bir işleç işlev çağrısı içinde gizlenmiş olabilir. Kullanıcı, belirtilen işlecin dikkatli olmanız gerekir `reduction` yan tümcesi, azaltma işlemi eşleşir.

Ancak sağ işleneninin &#124; &#124; işleci Bu örnekte yan etkileri varsa, izin verilen ancak dikkatli kullanılmalıdır. Bu bağlamda sıralı döngü yürütülmesi sırasında oluşan değil kesin bir yan etkisi, Paralel yürütme sırasında ortaya çıkabilir. Bu fark, tekrar yürütme sırası belirsiz olduğundan ortaya çıkabilir.

İşleci, azaltma için derleyici tarafından kullanılan tüm özel değişkenler ilk değerini belirlemek ve sonlandırma işleci belirlemek için kullanılır. İşleci açıkça belirtilmesi azaltma deyim yapısı sözcük kapsamı dışında olmasını sağlar. Herhangi bir sayıda `reduction` yönergesindeki yan tümceleri belirtilebilir, ancak bir değişkeni en fazla bir listede görünebilir `reduction` yan tümcesi bu yönergesi.

Her bir değişken özel bir kopyasını *değişken listesi* , her iş parçacığında oluşturulan gibi `private` yan tümcesi kullanılmış. Özel kopyalama işleci göre başlatılır (aşağıdaki tabloya bakın).

Hangi bölgeyi sonunda `reduction` yan tümcesi belirtilmiş, özgün nesne özgün değerine her belirtilen işlecini kullanarak özel kopyaları son değeri ile birleştirilmesinin sonucu yansıtacak şekilde güncelleştirilir. Azaltma işleçleri (çıkarma dışında) tüm ilişkilendirilir ve derleyici serbestçe son değeri hesaplama yeniden ilişkilendirin. (Bir çıkarma azaltma kısmi sonuçları son değer oluşturmak için eklenir.)

Orijinal nesnenin değeri ilk iş parçacığında içeren yan tümcesi ulaşır ve azaltma hesaplama işlemi tamamlanana kadar bunu kalırsa belirsiz hale gelir.  Normalde, hesaplama yapısı sonunda tamamlanmış olacaktır; Ancak, `reduction` yan tümcesi, bir yapı hangi ınternationalized `nowait` olan tüm iş parçacıklarının tamamladığınızdaneminolmakiçinbirengelleeşitlemegerçekleştirilenkadardauygulanan,orijinalnesnenindeğeribelirsizkalır`reduction`yan tümcesi.

Aşağıdaki tabloda, geçerli işleçler ve canonical başlatma değerlerini listeler. Gerçek başlangıç değerini azaltma değişkeni, veri türü ile tutarlı olur.

|İşleç|Başlatma|
|--------------|--------------------|
|+|0|
|&#42;|1.|
|-|0|
|&amp;|~0|
|&#124;|0|
|^|0|
|&amp;&amp;|1.|
|&#124;&#124;|0|

Kısıtlamaları `reduction` yan tümcesi aşağıdaki gibidir:

- Değişken türünü `reduction` işaretçi türleri ve başvuru türleri hiçbir zaman izin verilir, ancak yan tümcesi azaltma işleci için geçerli olmalıdır.

- Belirtilen değişken `reduction` yan tümcesi olmalıdır **const**-tam.

- Bir paralel bölgenin içinde özel olmayan veya, görünen değişkenleri `reduction` yan tümcesi bir **paralel** yönergesi belirtilemez bir `reduction` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```

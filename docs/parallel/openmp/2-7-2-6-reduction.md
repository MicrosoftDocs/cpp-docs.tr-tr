---
title: 2.7.2.6 azaltma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cbcb5cc6c4b01f3cbf996431435f42a7b034d002
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

Bu yan tümce azaltma görünmesini skaler değişkenleri gerçekleştirir *değişken listesi*, işleciyle *op*. Söz dizimi `reduction` yan tümcesi aşağıdaki gibidir:

> azaltma (*op*: *değişken listesi*)

Bir azaltma, genellikle aşağıdaki biçimlerden birini deyimiyle için belirtilir:

> *x* = *x* *op* *ifade*  
> *x* *binop* = *ifade*  
> *x* = *expr* *op* *x* (dışında çıkarma)  
> *x*++  
> ++*x*  
> *x*--  
> --*x*  

burada:

*x*  
Belirtilen azaltma değişkenlerinden biri `list`.

*değişken listesi*  
Skaler azaltma değişkenleri virgülle ayrılmış listesi.

*ifade*  
Bir ifade değil başvuru skaler bir tür ile *x*.

*OP*  
Aşırı yüklenmiş bir işleç ancak biri +, &#42; -, &amp;, ^, &#124; &amp; &amp;, veya &#124; &#124;.

*binop*  
Aşırı yüklenmiş bir işleç ancak biri +, &#42; -, &amp;, ^, veya &#124;.

Aşağıdaki örneğidir `reduction` yan tümcesi:  
  
```cpp  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
Örnekte gösterildiği gibi bir işleç işlev çağrısı içinde gizli olabilir. Kullanıcı işleci içinde belirtilen dikkatli olmalıdır `reduction` yan tümcesi azaltma işlemi eşleşir.

Ancak sağ işleneni, &#124; &#124; işleci Bu örnekte hiçbir yan etkisi vardır, izin verilen ancak dikkatli kullanılmalıdır. Bu bağlamda döngü sıralı yürütülmesi sırasında oluşan değil garanti bir yan etkisi Paralel yürütme sırasında ortaya çıkabilir. Yineleme yürütme sırasını belirsiz olduğundan bu fark ortaya çıkabilir.

İşleci, azaltma için derleyici tarafından kullanılan herhangi bir özel değişkeni başlangıç değerini belirler ve sonlandırma işleci belirlemek için kullanılır. İşleç açıkça belirtilmesi azaltma deyimi yapı sözcük kapsamı dışında olmasını sağlar. Herhangi bir sayıda `reduction` yan tümceleri üzerinde yönergesi belirtilebilir, ancak bir değişkeni en fazla birinde görünebilir `reduction` yan tümcesi bu yönergesi için.

Her bir değişken özel bir kopyasını *değişken listesi* , her iş parçacığı için bir tane oluşturulur gibi `private` yan tümcesi kullanıldı. Özel kopyayı göre işleci başlatılır (aşağıdaki tabloya bakın).

Hangi bölgeyi sonunda `reduction` yan tümcesi belirtilmiş, özgün nesne özgün değeri her belirtilen işlecini kullanarak özel kopyaları son değeri ile birleştirmenin sonucu yansıtacak şekilde güncelleştirilir. Azaltma işleçleri (çıkarma) dışında tüm ilişkilendirilebilir ve derleyici serbestçe son değeri hesaplama yeniden ilişkilendirin. (Bir çıkarma azaltma kısmi sonuçlarını son değeri form eklenir.)

İlk iş parçacığı içeren yan tümcesi ulaştığında ve azaltma hesaplama tamamlanana kadar bunu kalır özgün nesne değerini belirsiz olur.  Normalde, hesaplama yapı sonunda tamamlanmış olur; Ancak, varsa `reduction` yan tümcesi olan bir yapı üzerinde kullanılan `nowait` olan tüm iş parçacıklarının tamamladığınızdaneminolmakiçinbirengelleeşitlemegerçekleştirilenkadardegeçerlideğerözgünnesnebelirsizkalır`reduction`yan tümcesi.

Aşağıdaki tabloda, geçerli işleçler ve kurallı başlatma değerleri listelenmektedir. Gerçek başlangıç değerini azaltma değişkeninin veri türü ile tutarlı olur.

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

- Değişkenlerde türünü `reduction` işaretçi türleri ve başvuru türleri hiçbir zaman izin verilir ancak bu yan tümcesi azaltma işleci için geçerli olmalıdır.

- Belirtilen bir değişken `reduction` yan tümcesi olmamalıdır **const**-tam.

- Paralel bir bölge içinde özel olan veya görünen değişkenleri `reduction` yan tümcesinde bir **paralel** yönergesi belirtilemez bir `reduction` paralel yapı bağlar iş paylaşım bir yönergesi yan tümcesi.

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

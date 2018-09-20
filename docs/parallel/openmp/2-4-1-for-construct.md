---
title: 2.4.1 yapı için | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 27d2cbce-786b-4819-91d3-d55b2cc57a5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb9a554d9141223be7a5f6bc741c86b8f03511e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428555"
---
# <a name="241-for-construct"></a>2.4.1 Yapı için

**İçin** yönergesi ilişkili döngü yinelemesi paralel olarak yürütülen belirten bir yinelemeli iş paylaşımı yapısı tanımlar. Yinelemeleri **için** döngü bağlar, paralel yapı yürütme takımda zaten iş parçacıkları arasında dağıtılır. Söz dizimi **için** yapısı şu şekildedir:

```
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Yan tümcesi aşağıdakilerden biridir:

**Özel (** *değişken listesi* **)**

**firstprivate (** *değişken listesi* **)**

**lastprivate (** *değişken listesi* **)**

**azaltma (** *işleci* **:** *değişken listesi* **)**

**Sıralı**

**zamanlama (** *tür* [**,** *chunk_size*] **)**

**nowait**

**İçin** yönergesi yerleştirir kısıtlamaları yapısına karşılık gelen **için** döngü. Özellikle, karşılık gelen **için** döngü kurallı şekli olması gerekir:

**için (** *init-expr* **;** *var op mantıksal b*; *ıncr-expr* **)**

*init-expr*<br/>
Aşağıdakilerden biri:

*Varyasyon* = *lb*

*tamsayı türü var* = *lb*

*incr-expr*<br/>
Aşağıdakilerden biri:

++ *var*

*var* ++

-- *var*

*var* --

*Varyasyon* += *ıncr*

*Varyasyon* -= *ıncr*

*Varyasyon* = *var* + *ıncr*

*Varyasyon* = *ıncr* + *var*

*Varyasyon* = *var* - *ıncr*

*var*<br/>
Bir işaretli tamsayı değişken. Bu değişken aksi paylaşılabilir değilse, örtük olarak özel süresince yapılan **için**.   Bu değişken gövdesinden değiştirilmemelidir **için** deyimi. Değişken belirtilmediği sürece **lastprivate**, döngü belirsiz olduğunda değeri.

*mantıksal işlem*<br/>
Aşağıdakilerden biri:

<

\<=

>

\>=

*lb*, *b*, ve *ıncr*<br>
Tamsayı sabit ifadeleri döngü. Eşitleme sırasında bu ifadelerin değerlendirme yoktur. Bu nedenle, değerlendirilen tüm yan etkileri belirsiz sonuçlar.

Kurallı biçimi döngüde girişine hesaplanmasını döngü yinelemesi sayısını verildiğini unutmayın. Bu hesaplama türündeki değerlerle gerçekleştirilir *var*, integral yükseltmeler sonra. Özellikle, değerini *b* - *lb* + *ıncr* sonuç türü belirsiz olması gösterilemez. Daha fazla, ise *op mantıksal* olan < veya \<ardından = *ıncr-expr* koymasına *var* döngünün her yinelenişinde artırmak için.   Varsa *op mantıksal* olan > veya > ardından = *ıncr-expr* koymasına *var* döngünün her yinelenişinde azaltmak için.

**Zamanlama** yan tümcesi belirtir nasıl yinelemeleri **için** döngü takım iş parçacıkları arasında bölünür. Belirli bir yinelemeye hangi iş parçacığının yürütür üzerinde bir program doğruluğunu bağımlı olmamalıdır. Değerini *chunk_size*, belirtilmişse, pozitif bir değer ile bir döngü sabit tamsayı ifade olmalıdır. Bu ifadenin değerlendirilmesi sırasında eşitleme yoktur. Bu nedenle, değerlendirilen tüm yan etkileri belirsiz sonuçlar. Zamanlama *tür* aşağıdakilerden biri olabilir:

Tablo 2-1 **zamanlama** yan tümcesi *tür* değerleri

|||
|-|-|
|static|Zaman **zamanlama (statik,** *chunk_size* **)** belirtilirse, yinelemeleri tarafından belirtilen bir boyut parçalara bölünmüştür *chunk_size*. Öbekleri ettirirsiniz iş parçacığı numarası sırasına göre takım iş parçacıkları statik olarak atanır. Hiçbir *chunk_size* belirtilirse, yineleme alanı ile her bir iş parçacığı için atanmış bir öbek boyutu, yaklaşık olarak eşit olan parçalara bölünür.|
|dinamik|Zaman **zamanlama (dinamik** *chunk_size* **)** belirtilirse, yinelemeleri parçalar halinde her içeren bir dizi bölünmüştür *chunk_size* yineleme. Her öbek için bir atama bekleyen iş parçacığı atanır. İş parçacığı öbek tekrar yürütür ve atanacak hiçbir öbekleri kalana kadar sonraki ataması için bekler. Atanacak son öbek daha küçük bir yineleme sayısı gerekebileceğini unutmayın. Hiçbir *chunk_size* belirtilirse, varsayılan olarak, 1 olur.|
|Destekli|Zaman **zamanlama (Kılavuzlu,** *chunk_size* **)** belirtilirse, yinelemeleri öbek boyutları azaltma ile iş parçacıklarının atanır. Bir iş parçacığı kendi atanan öbek yinelemelerin sona erdiğinde, hiçbiri kalana kadar dinamik olarak başka bir öbek atanır. İçin bir *chunk_size* 1, her öbek boyutu yaklaşık iş parçacıklarının sayıya bölünen atanmamış yinelemeler sayısıdır. Bu boyutları yaklaşık 1 katlanarak azaltın. İçin bir *chunk_size* değerle *k* 1 ' den büyük boyutları yaklaşık katlanarak ye azaltmak *k*son öbek daha az olabilir, ancak  *k* yineleme. Hiçbir *chunk_size* belirtilirse, varsayılan olarak, 1 olur.|
|çalışma zamanı|Zaman **schedule(runtime)** belirtilirse, ilgili planlama çalışma zamanına kadar ertelenmiş karar. Zamanlama *tür* ve Öbek boyutu seçilebilir çalışma zamanında ortam değişkenini ayarlayarak **OMP_SCHEDULE**. Bu ortam değişkeni ayarlanmazsa, sonuçta elde edilen zamanlama uygulama tarafından tanımlanır. Zaman **schedule(runtime)** belirtilen *chunk_size* belirtilmemelidir.|

Açıkça tanımlanmış olmadığında **zamanlama** yan tümcesi, varsayılan **zamanlama** uygulama tarafından tanımlanır.

OpenMP uyumlu bir program, doğru yürütme için belirli bir zamanlama dayanarak doğrulamamalısınız. Bir program bir zamanlamaya göre doğrulamamalısınız *tür* aynı zamanlama uygulamalarında Çeşitlemeler olmasını mümkün olduğu için tam olarak yukarıda verilen açıklama uyumludur *tür* arasında farklı derleyicileri. Açıklamalar, belirli bir durum için uygun olan zamanlamayı seçin için kullanılabilir.

**Sıralı** yan tümcesi bulunmalıdır ne zaman **sıralı** bağlanma yönergeleri **için** oluşturun.

Sonunda örtük bir engel olan bir **için** sürece oluşturmak bir **nowait** yan tümcesi belirtildi.

Kısıtlamaları **için** yönerge aşağıdaki gibidir:

- **İçin** döngü yapısal bloğunun olmalıdır ve ayrıca, yürütme ile bitmelidir değil bir **sonu** deyimi.

- Döngü değerlerini denetim ifadeleri **için** döngü ile ilişkili bir **için** yönergesi takım iş parçacıkları için aynı olması gerekir.

- **İçin** döngüsünün yineleme değişkeni işaretli bir tamsayı türü olmalıdır.

- Yalnızca tek bir **zamanlama** yan tümcesi görüntülenebilir bir **için** yönergesi.

- Yalnızca tek bir **sıralı** yan tümcesi görüntülenebilir bir **için** yönergesi.

- Yalnızca tek bir **nowait** yan tümcesi görüntülenebilir bir **için** yönergesi.

- Belirtilmeyen if veya ne sıklıkta içindeki tüm yan etkiler olan *chunk_size*, *lb*, *b*, veya *ıncr* ifadeleri oluşur.

- Değerini *chunk_size* ifade takımın tüm iş parçacıkları için aynı olması gerekir.

## <a name="cross-references"></a>Başvuruları çapraz:

- **özel**, **firstprivate**, **lastprivate**, ve **azaltma** yan tümcesi bkz [bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.

- **OMP_SCHEDULE** ortam değişkeni, bkz: [bölümü 4.1](../../parallel/openmp/4-1-omp-schedule.md) sayfasında 48.

- **Sıralı** oluşturmak için bkz: [bölümü 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) sayfasında 22.

- [Ek D](../../parallel/openmp/d-using-the-schedule-clause.md), sayfa 93, zamanlama yan tümcesini hakkında daha fazla bilgi sağlar.
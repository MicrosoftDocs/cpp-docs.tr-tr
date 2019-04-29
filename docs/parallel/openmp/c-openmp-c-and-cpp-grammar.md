---
title: C. OpenMP C ve C++ dil bilgisi
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 85e18161079b49e83cc9fedb3184ee220c889e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362952"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP C ve C++ dil bilgisi

[C.1 Gösterim](#c1-notation)<br/>
[C.2 Kurallar](#c2-rules)

## <a name="c1-notation"></a>C.1 Gösterim

Bir terminal olmayan, adının dilbilgisi kuralları oluşur değiştirme alternatifleri tarafından ayrı satırlarda üste, ardından.

Söz dizimi ifade terimi<sub>iyileştirilmiş</sub> dönem içinde değişiklik isteğe bağlı olduğunu gösterir.

Söz dizimi ifade *terimi*<sub>optseq</sub> eşdeğerdir *terimi-seq*<sub>iyileştirilmiş</sub> aşağıdaki ek kuralları ile:

*Terim-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*Terim*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq* *term*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq*   `,` *term*

## <a name="c2-rules"></a>C.2 Kurallar

Gösterimi, standart C 6.1 bölümünde açıklanmıştır. Bu dil bilgisi ek OpenMP C ve C++ yönergeleri için temel dil dilbilgisi uzantılarını göstermektedir.

**/\* in C++ (ISO/IEC 14882:1998) \*/**

*deyimi-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deyimi-seq deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deyimi-seq openmp yönergesi*

**/\* in C90 (ISO/IEC 9899:1990) \*/**

*ifade listesinin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade listesinin deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade listesinin openmp yönergesi*

**/\* in C99 (ISO/IEC 9899:1999) \*/**

*Blok öğesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP yönergesi*

**/\* Standart deyimleri \*/**

*deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP yapısı*

*OpenMP yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yapısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı için*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bölümler yapısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tek yapısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Yapı için Parallel*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel bölümleri yapısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ana yapısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Critical yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıralı yapısı*

*OpenMP yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*barrier yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush yönergesi*

*Yapısal blok*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*

*Paralel yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yönergesi yapısal blok*

*Paralel yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel` *Paralel yan tümcesi*<sub>optseq</sub> *yeni satır*

*Paralel yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*

*Paralel yan benzersiz*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (` *İfade*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (` *İfade*   `)`

*Yapı için*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yönergesi için yineleme deyimi*

*yönergesi için*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for` *yan tümcesi için*<sub>optseq</sub> *yeni satır*

*yan tümcesi için*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*for yan benzersiz*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *zamanlama türü*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *zamanlama türü* `,` *ifadesi*   `)`

*zamanlama türü*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*bölümler yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bölüm yönergesi bölümüne kapsamı*

*Bölüm yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections` *bölümler yan tümcesi*<sub>optseq</sub> *yeni satır*

*bölümler yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*Kapsam bölümü*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{Bölüm dizisi}*

*Bölüm dizisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bölüm yönergesi*<sub>iyileştirilmiş</sub> *yapısal blok*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bölüm dizisi bölüm yönergesi yapısal blok*

*Bölüm yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section` *Yeni satır*

*tek yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tek yönergesi yapısal blok*

*tek yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single` *tek yan tümceli*<sub>optseq</sub> *yeni satır*

*tek yan tümceli*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*Yapı için Parallel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yönergesi için paralel yineleme deyimi*

*yönergesi için paralel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for` *Paralel for yan*<sub>optseq</sub> *yeni satır*

*Paralel for yan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*

*Paralel bölümleri yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel bölümleri yönergesi bölümüne kapsamı*

*Paralel bölümleri yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections` *Paralel bölümleri yan*<sub>optseq</sub> *yeni satır*

*Paralel bölümleri yan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*

*Ana yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ana yönergesi yapısal blok*

*Ana yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master` *Yeni satır*

*Critical yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Critical yönergesini yapısal blok*

*Critical yönergesini*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical` *Bölge ifade*<sub>iyileştirilmiş</sub> *yeni satır*

*Bölge ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(tanımlayıcı)*

*barrier yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier` *Yeni satır*

*atomic yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic yönergesini ifade deyimi*

*atomic yönergesini*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic` *Yeni satır*

*Flush yönergesini*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush` *Flush değişkenleri*<sub>iyileştirilmiş</sub> *yeni satır*

*Flush değişkenleri*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(değişken-listesi)*

*sıralı yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıralı yönergesi yapısal blok*

*sıralı yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered` *Yeni satır*

**/\* Standart bildirimleri \*/**

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate yönergesi*

*threadprivate yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (` *değişken listesi* `)` *yeni satır*

*Veri yan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (` *değişken listesi*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (` *değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (` *değişken listesi*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *Azaltma işleci*`:`*değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *değişken listesi*    `)`

*Azaltma işleci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Biri:   `+ \* - & ^ | && ||`

**/\* C \*/**

*değişken listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*değişken listesi* `,` *tanımlayıcısı*

**/\* c++'ta \*/**

*değişken listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deyim kimliği*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*değişken listesi* `,` *kimliği ifadesi*

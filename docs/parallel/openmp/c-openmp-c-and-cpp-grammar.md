---
description: 'Daha fazla bilgi edinin: C. OpenMP C ve C++ dilbilgisi'
title: C. OpenMP C ve C++ dil bilgisi
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 9543d721afbff1069b5497ba8dc7092089a1b706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342510"
---
# <a name="c-openmp-c-and-c-grammar"></a>C. OpenMP C ve C++ dil bilgisi

[C.1 Gösterim](#c1-notation)<br/>
[C.2 Kurallar](#c2-rules)

## <a name="c1-notation"></a>C.1 Gösterim

Dilbilgisi kuralları, terminal dışı bir, ardından iki nokta üst üste ve ardından ayrı satırlardaki değiştirme alternatifleri ile oluşur.

Sözdizimsel ifade terimi<sub>kabul etme</sub> , terimin değiştirme içinde isteğe bağlı olduğunu gösterir.

Sözdizimi ifade *terimi*<sub>seçeneksırası</sub> , aşağıdaki ek kurallarla *terim sırası*<sub>kabul etme</sub> ile eşdeğerdir:

*terim sırası*:  
&nbsp;&nbsp;&nbsp;&nbsp;*terimli*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*terim sırası* *terimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*terim-sıra* `,` *terim*   

## <a name="c2-rules"></a>C.2 Kurallar

Gösterim, C standardının 6,1 bölümünde açıklanmaktadır. Bu dilbilgisi eki, OpenMP C ve C++ yönergeleri için temel dil dilbilgisinde uzantıları gösterir.

**/\* C++ ' da (ISO/ıEC 14882:1998) \*/**

*Ekstre-sıra*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP-yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre-Seq ekstresi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre-Seq OpenMP-Directive*

**/\* C90 içinde (ISO/ıEC 9899:1990) \*/**

*Ekstre-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP-yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre-List ekstresi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade-List OpenMP-Directive*

**/\* C99 içinde (ISO/ıEC 9899:1999) \*/**

*blok-öğe*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bağımsız*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP-yönergesi*

**/\* Standart deyimler \*/**

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP-yapı*

*OpenMP-yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*paralel yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for-yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bölümler-yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tek yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*paralel-for-yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*paralel-bölümler-yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ana yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Kritik-yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Atomik yapı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıralı-yapı*

*OpenMP-yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bariyer-yönerge*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush-yönergesi*

*yapılandırılmış blok*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ekstre*

*paralel yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-Directive yapılandırılmış bloğu*

*Parallel-Directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel`*Parallel yan tümce*<sub>seçeneksırası</sub> *yeni satır*

*Parallel-yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Unique-Parallel-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-yan tümcesi*

*Unique-Parallel-yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (`*ifade*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (`*ifade*   `)`

*için-yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for-Directive yineleme-ekstresi*

*for-yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for`*for-Clause*<sub>seçeneksırası</sub> *yeni satır*

*for-yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Unique-for-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*Unique-for-yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*zamanlama türü*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (`*zamanlama türü* `,` *ifade*      `)`

*zamanlama-tür*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*bölümler-yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sections-Directive bölüm-kapsam*

*bölümler-yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections`*sections-yan tümce*<sub>seçeneksırası</sub> *yeni-satır*

*sections-yan tümce*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*bölüm kapsamı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{Section-Sequence}*

*bölüm sırası*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bölüm-yönerge*<sub>opt</sub> *yapılandırılmış-blok*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bölüm-dizi bölümü-yönerge yapılandırılmış-blok*

*bölüm-yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section`*yeni satır*

*tek yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tek yönergeyle yapılandırılmış blok*

*tek yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single`*tek yan tümce*<sub>seçeneksırası</sub> *yeni satır*

*Single yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*:*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-for-Directive yineleme-ekstresi*

*Parallel-for-yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for`*Parallel-for-yan tümcesi*<sub>seçeneksırası</sub> *yeni satır*

*Parallel-for-yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Unique-Parallel-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Unique-for-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-yan tümcesi*

*paralel-bölümler-yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Parallel-sections-Directive bölümü-kapsam*

*paralel-bölümler-yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections`*Parallel-sections-yan tümce*<sub>seçeneksırası</sub> *yeni-satır*

*Parallel-sections-yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Unique-Parallel-yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Data-yan tümcesi*

*ana yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ana yönerge yapılandırılmış-blok*

*ana yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master`*yeni satır*

*kritik-yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*kritik-yönerge yapılandırılmış blok*

*kritik-yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical`*bölge tümceciği*<sub>katılım</sub> *yeni satırı*

*bölge tümceciği*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

*engel-yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier`*yeni satır*

*atomik yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Atomik yönerge ifadesi-deyim*

*atomik yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic`*yeni satır*

*Flush-yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush`*Flush-VARS*<sub>opt</sub> *yeni satır*

*Flush-VARS*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(değişken listesi)*

*sıralı-yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıralı-yönerge yapılandırılmış-blok*

*sıralı-yönerge*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered`*yeni satır*

**/\* Standart bildirimler \*/**

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate-yönergesi*

*threadprivate-yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (`*değişken listesi* `)` *yeni satır*    

*veri yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (`*değişken listesi*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (`*değişken listesi*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (`*değişken listesi*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *azaltma-işleç* `:` *değişken listesi*          `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *değişken listesi*    `)`

*azaltma-işleç*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Aşağıdakilerden biri:   `+ \* - & ^ | && ||`

**/\* C 'de \*/**

*değişken listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*değişken listesi* `,` *tanımlayıcı*   

**/\* C++ ' da \*/**

*değişken listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*kimlik ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*değişken listesi* `,` *kimlik ifadesi*   

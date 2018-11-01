---
title: C.2 Kurallar
ms.date: 11/04/2016
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
ms.openlocfilehash: 7c0de4c14e229716bcf764d9859be439090368b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642812"
---
# <a name="c2-rules"></a>C.2 Kurallar

Gösterimi, standart C 6.1 bölümünde açıklanmıştır. Bu dil bilgisi ek OpenMP C ve C++ yönergeleri için temel dil dilbilgisi uzantılarını göstermektedir.

**/\* C++'da (ISO/IEC 14882:1998) \*/**

*deyimi-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deyimi-seq deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deyimi-seq openmp yönergesi*

**/\* C90 içinde (ISO/IEC 9899:1990) \*/**

*ifade listesinin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP yönergesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade listesinin deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade listesinin openmp yönergesi*

**/\* C99 içinde (ISO/IEC 9899:1999) \*/**

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
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp parallel** *paralel yan tümcesi*<sub>optseq</sub> *yeni satır*

*Paralel yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*

*Paralel yan benzersiz*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**varsa (** *ifade* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**num_threads (** *ifade* **)**

*Yapı için*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yönergesi için yineleme deyimi*

*yönergesi için*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp için** *yan tümcesi için*<sub>optseq</sub> *yeni satır*

*yan tümcesi için*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*for yan benzersiz*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Sıralı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**zamanlama (** *zamanlama türü* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**zamanlama (** *zamanlama türü* **,** *ifade* **)**

*zamanlama türü*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Statik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Dinamik**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Destekli**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Çalışma zamanı**

*bölümler yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bölüm yönergesi bölümüne kapsamı*

*Bölüm yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp bölümleri** *bölümleri yan tümcesi*<sub>optseq</sub> *yeni satır*

*bölümler yan tümcesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*Kapsam bölümü*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{Bölüm dizisi}*

*Bölüm dizisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bölüm yönergesi*<sub>iyileştirilmiş</sub> *yapısal blok*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bölüm dizisi bölüm yönergesi yapısal blok*

*Bölüm yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp bölümünde** *yeni satır*

*tek yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tek yönergesi yapısal blok*

*tek yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp tek** *tek yan tümceli*<sub>optseq</sub> *yeni satır*

*tek yan tümceli*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*Yapı için Parallel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*yönergesi için paralel yineleme deyimi*

*yönergesi için paralel*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp parallel için** *paralel for yan*<sub>optseq</sub> *yeni satır*

*Paralel for yan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*for yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*

*Paralel bölümleri yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel bölümleri yönergesi bölümüne kapsamı*

*Paralel bölümleri yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp paralel bölümleri** *paralel bölümleri yan*<sub>optseq</sub> *yeni satır*

*Paralel bölümleri yan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Paralel yan benzersiz*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Veri yan tümcesi*

*Ana yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Ana yönergesi yapısal blok*

*Ana yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp ana** *yeni satır*

*Critical yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Critical yönergesini yapısal blok*

*Critical yönergesini*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp kritik** *bölge ifade*<sub>iyileştirilmiş</sub> *yeni satır*

*Bölge ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(tanımlayıcı)*

*barrier yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp engel** *yeni satır*

*atomic yapı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atomic yönergesini ifade deyimi*

*atomic yönergesini*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp atomic** *yeni satır*

*Flush yönergesini*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp Temizleme** *temizleme değişkenleri*<sub>iyileştirilmiş</sub> *yeni satır*

*Flush değişkenleri*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(değişken-listesi)*

*sıralı yapısı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıralı yönergesi yapısal blok*

*sıralı yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp sıralı** *yeni satır*

**/\* Standart bildirimleri \*/**

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*threadprivate yönergesi*

*threadprivate yönergesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# pragma omp threadprivate (** *değişken listesi***)** *yeni satır*

*Veri yan*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Özel (** *değişken listesi* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**copyprivate (***değişken listesi***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**firstprivate (***değişken listesi***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**lastprivate (** *değişken listesi***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Paylaşılan (** *değişken listesi* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan (paylaşılan)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Varsayılan (hiçbiri)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**azaltma (***azaltma işleci***:***değişken listesi***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**copyin (***değişken listesi***)**

*Azaltma işleci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Şunlardan biri:  **+  \* -& ^ &#124; & &&#124;&#124;**

**/\* C \*/**

*değişken listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*değişken listesi* **,** *tanımlayıcısı*

**/\* c++'ta \*/**

*değişken listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*deyim kimliği*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*değişken listesi* **,** *kimliği ifadesi*
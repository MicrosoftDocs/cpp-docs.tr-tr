---
title: C.2 kurallar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5efa8d0e7cf4118362b7695bafcd4710b4021f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c2-rules"></a>C.2 Kurallar
Gösterimi standart C 6.1 bölümünde açıklanmıştır. Bu dilbilgisi ek OpenMP C ve C++ yönergeleri için temel dil dilbilgisi uzantıları gösterir.  
  
 **/\*C++ (ISO/IEC 14882:1998)\*/**  
  
 *deyimi seq*:  
  
 *deyimi*  
  
 *OpenMP yönergesi*  
  
 *deyimi seq deyimi*  
  
 *deyimi seq openmp yönergesi*  
  
 **/\*C90 içinde (ISO/IEC 9899:1990)\*/**  
  
 *Ekstre listesini*:  
  
 *deyimi*  
  
 *OpenMP yönergesi*  
  
 *deyimi listesi deyimi*  
  
 *Ekstre listesini openmp yönergesi*  
  
 **/\*C99 içinde (ISO/IEC 9899:1999)\*/**  
  
 *Blok öğesi*:  
  
 *bildirimi*  
  
 *deyimi*  
  
 *OpenMP yönergesi*  
  
 *deyimi*:  
  
 **/\*Standart deyimleri\*/**  
  
 *OpenMP yapısı*  
  
 *OpenMP yapı*:  
  
 *Paralel yapı*  
  
 *Yapı için*  
  
 *bölümler yapısı*  
  
 *tek yapısı*  
  
 *Yapı için Parallel*  
  
 *Paralel bölümleri yapısı*  
  
 *Ana construc*  
  
 *Critical yapı*  
  
 *atomic yapı*  
  
 *sıralı yapısı*  
  
 *OpenMP yönergesi*:  
  
 *barrier yönergesi*  
  
 *Flush yönergesi*  
  
 *yapılandırılmış blok*:  
  
 *deyimi*  
  
 *Paralel yapı*:  
  
 *Paralel yönergesi yapılandırılmış bloğu*  
  
 *Paralel yönergesi*:  
  
 **# pragma omp paralel***paralel yan tümcesi*optseq *yeni satır*   
  
 *Paralel yan tümcesi*:  
  
 *Paralel yan benzersiz*  
  
 *Veri yan tümcesi*  
  
 *Paralel yan benzersiz*:  
  
 **varsa (** *ifade* **)**  
  
 **num_threads (** *ifade* **)**  
  
 *Yapı için*:  
  
 *yönergesi için yineleme-deyimi*  
  
 *yönergesi için*:  
  
 **# pragma omp** *yan tümcesi için*optseq *yeni satır*  
  
 *yan tümcesi için*:  
  
 *for yan benzersiz*  
  
 *Veri yan tümcesi*  
  
 **nowait**  
  
 *for yan benzersiz*:  
  
 **sıralı**  
  
 **zamanlama (** *zamanlama türü* **)**  
  
 **zamanlama (** *zamanlama türü* **,** *ifade* **)**  
  
 *zamanlama türü*:  
  
 **static**  
  
 **dynamic**  
  
 **Destekli**  
  
 **çalışma zamanı**  
  
 *bölümler yapı*:  
  
 *bölümler yönergesi bölüm kapsamı*  
  
 *bölümler yönergesi*:  
  
 **# pragma omp bölümleri** *bölümleri yan tümcesi*optseq *yeni satır*  
  
 *bölümler yan tümcesi*:  
  
 *Veri yan tümcesi*  
  
 **nowait**  
  
 *Bölüm kapsam*:  
  
 *{sıralı bölümü}*  
  
 *Bölüm sırası*:  
  
 *Bölüm yönergesi*kabul *yapılandırılmış bloğu*  
  
 *Bölüm Sırası bölüm yönergesi yapılandırılmış bloğu*  
  
 *Bölüm yönergesi*:  
  
 **# pragma omp bölüm** *yeni satır*  
  
 *tek yapı*:  
  
 *tek yönergesi yapılandırılmış bloğu*  
  
 *tek yönergesi*:  
  
 **# pragma omp tek** *tek yan tümcesi*optseq *yeni satır*  
  
 *tek yan tümcesi*:  
  
 *Veri yan tümcesi*  
  
 **nowait**  
  
 *Yapı için Parallel*:  
  
 *yönergesi için paralel yineleme-deyimi*  
  
 *yönergesi için paralel*:  
  
 **# pragma omp için paralel** *paralel için yan tümcesi*optseq *yeni satır*  
  
 *Paralel için yan tümcesi*:  
  
 *Paralel yan benzersiz*  
  
 *for yan benzersiz*  
  
 *Veri yan tümcesi*  
  
 *Paralel bölümleri yapı*:  
  
 *Paralel bölümleri yönergesi bölüm kapsamı*  
  
 *Paralel bölümleri yönergesi*:  
  
 **# pragma omp paralel bölümleri** *paralel bölümleri yan*optseq *yeni satır*  
  
 *Paralel bölümleri yan*:  
  
 *Paralel yan benzersiz*  
  
 *Veri yan tümcesi*  
  
 *Master yapı*:  
  
 *Master yönergesi yapılandırılmış bloğu*  
  
 *Master yönergesi*:  
  
 **# pragma omp ana** *yeni satır*  
  
 *Critical yapı*:  
  
 *yönergesi kritik yapılandırılmış bloğu*  
  
 *yönergesi kritik*:  
  
 **# pragma omp kritik** *bölge tümcecik*kabul *yeni satır*  
  
 *Bölge tümcecik*:  
  
 *(tanımlayıcı)*  
  
 *barrier yönergesi*:  
  
 **# pragma omp engel** *yeni satır*  
  
 *atomic yapı*:  
  
 *yönergesi atomik ifade deyimi*  
  
 *yönergesi atomik*:  
  
 **# pragma omp atomik** *yeni satır*  
  
 *Flush yönergesi*:  
  
 **# pragma omp Temizleme** *temizleme değişkenleri*kabul *yeni satır*  
  
 *Flush değişkenleri*:  
  
 *(liste değişken)*  
  
 *sıralı yapı*:  
  
 *sıralı yönergesi yapılandırılmış bloğu*  
  
 *sıralı yönergesi*:  
  
 **# pragma omp sıralı** *yeni satır*  
  
 *bildirim*:  
  
 **/\*Standart bildirimleri\*/**  
  
 *threadprivate yönergesi*  
  
 *threadprivate yönergesi*:  
  
 **# pragma omp threadprivate (** *değişken listesi***)** *yeni satır*   
  
 *Veri yan tümcesi*:  
  
 **Özel (** *değişken listesi* **)**  
  
 **copyprivate (***değişken listesi***)**   
  
 **firstprivate (***değişken listesi***)**   
  
 **lastprivate (** *değişken listesi***)**   
  
 **Paylaşılan (** *değişken listesi* **)**  
  
 **Varsayılan (paylaşılan)**  
  
 **Varsayılan (yok)**  
  
 **azaltma (***azaltma işleci***:***değişken listesi***)**   
  
 **copyin (***değişken listesi***)**   
  
 *Azaltma işleci*:  
  
 *Aşağıdakilerden birini*:  **+  \* -& ^ &#124; & & &#124; &#124;**  
  
 **/\*C\*/**  
  
 *değişken listesi*:  
  
 *tanımlayıcı*  
  
 *değişken listesi* **,** *tanımlayıcısı*  
  
 **/\*C++'da\*/**  
  
 *değişken listesi*:  
  
 *Kimliği ifade*  
  
 *değişken listesi* **,** *kimliği ifade*
---
title: "2.7.2 veri paylaşım öznitelik yan tümceleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e3fbc78792034c60c94972ca6b4ed63dfac01b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 Veri Paylaşım Öznitelik Yan Tümceleri
Birkaç yönergeleri, bir kullanıcının değişkenleri paylaşım özniteliklerini bölge süresince denetlemesine izin ver yan tümceleri kabul edin. Paylaşım öznitelik yan tümceleri yalnızca sözcük tümcesi göründüğü yönergesi kapsamını değişkenleri uygulanır. Aşağıdaki yan tümceleri tüm tüm yönergelerinde izin verilir. Belirli bir yönergeyi üzerinde geçerli yan tümceleri listesi yönergesiyle açıklanmıştır.  
  
 Bir değişken paralel zaman görünür ise veya iş paylaşım yapısıyla karşılaştı ve değişken bir paylaşım öznitelik yan tümcesinde belirtilmediğinden veya **threadprivate** yönerge, ardından değişkeni paylaşılır. Statik değişkenler paralel bir bölge dinamik kapsam içinde bildirilen paylaşılır. Yığın bellek tahsis (örneğin, kullanarak **malloc()** C veya C++ veya **yeni** işleci C++'ta) paylaşılır. (Bu bellek işaretçisine ancak, özel veya paylaşılan olabilir.) Otomatik depolama süresi paralel bir bölge dinamik kapsam içinde bildirilen değişkenlerle özeldir.  
  
 Yan tümceler çoğunu kabul bir *değişken listesi* görünür değişkenleri virgülle ayrılmış bir listesi bağımsız değişkeni. Bir değişken başvurulan bir veri paylaşım öznitelik yan tümcesi bir şablondan türetilmiş bir tür vardır ve programın bu değişken bir başvuruları vardır, tanımlanmamış bir davranıştır.  
  
 Yönerge yan tümceleri içinde görünür tüm değişkenleri görünür olması gerekir. Yan tümceleri yinelenen gerektiği gibi ancak bir değişken her ikisinde de belirtilebilir dışında hiçbir değişken birden fazla yan tümcesinde belirtilen bir **firstprivate** ve **lastprivate** yan tümcesi.  
  
 Aşağıdaki bölümlerde, veri paylaşım öznitelik yan tümceleri açıklanmaktadır:  
  
-   **özel**, [bölüm 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25.  
  
-   **firstprivate**, [bölüm 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) sayfasında 26.  
  
-   **lastprivate**, [bölüm 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) 27 sayfasında.  
  
-   **Paylaşılan**, [bölüm 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) 27 sayfasında.  
  
-   **Varsayılan**, [bölüm 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) sayfasında 28.  
  
-   **azaltma**, [bölüm 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) sayfasında 28.  
  
-   **copyin**, [bölüm 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) sayfasında 31.  
  
-   **copyprivate**, [bölüm 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) 32 sayfasında.
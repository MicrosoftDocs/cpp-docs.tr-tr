---
title: "2.6.5 flush yönergesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7607070692941606b863be9248b2d69f093f3a13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="265-flush-directive"></a>2.6.5 flush Yönergesi
**Flush** yönergesi, açık veya zımni, olup olmadığını belirtir uygulama bir takım tüm iş parçacıkları (aşağıda belirtilen) belirli nesnelerin tutarlı bir görünümünü sağlamak için gereken bir "iş parçacıkları arası" dizi noktası bellek. Bu nesnelere başvuran bir ifade önceki değerlendirmeleri tamamlandığından ve sonraki değerlendirmeleri değil henüz başlamıştır anlamına gelir. Örneğin, derleyicileri nesneleri değerlerini kayıtları belleği geri yüklemeniz gerekir ve donanım yazma arabellekleri için bellek temizleme ve nesneleri bellekten değerlerini yeniden gerekebilir.  
  
 Söz dizimi **flush** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp flush [(variable-list)]  new-line  
```  
  
 Eşitleme gerektiren nesnelerini tüm değişkenleri tarafından belirlenebilir sonra bu değişkenleri isteğe bağlı olarak belirtilebilir *değişken listesi*. Bir işaretçi varsa, *değişken listesi*işaretçi Temizlenen, işaretçi başvurduğu nesnesi değil.  
  
 A **Temizleme** olmadan yönerge bir *değişken listesi* erişilemez nesneleri dışında tüm paylaşılan nesneleri otomatik depolama süresi ile eşitler. (Bu daha fazla yükü yükünden daha fazladır büyük olasılıkla bir **Temizleme** ile bir *değişken listesi*.) A **Temizleme** olmadan yönerge bir *değişken listesi* için aşağıdaki yönergeleri kapsanan:  
  
-   `barrier`  
  
-   İçin giriş ve çıkış ' **kritik**  
  
-   İçin giriş ve çıkış '`ordered`  
  
-   İçin giriş ve çıkış ' **paralel**  
  
-   AT çıkmak **için**  
  
-   AT çıkmak **bölümleri**  
  
-   AT çıkmak **tek**  
  
-   İçin giriş ve çıkış ' **için paralel**  
  
-   İçin giriş ve çıkış ' **paralel bölümleri**  
  
 Yönergesi varsa kullanılmaz bir `nowait` yan tümcesi varsa. Dikkat edilmesi gereken, **flush** yönergesi değil kapsanan aşağıdakilerden biri:  
  
-   Girişe adresindeki **için**  
  
-   İçin giriş veya çıkış ' **ana**  
  
-   Girişe adresindeki **bölümleri**  
  
-   Girişe adresindeki **tek**  
  
 Bir geçici nitelenmiş tür sahip bir nesne değeri erişen bir başvuru vardı gibi davranır bir **flush** söz konusu nesne önceki dizisi noktada belirtme yönergesi. Bir geçici nitelenmiş tür sahip bir nesne değerini değiştiren bir başvuru vardı gibi davranır bir **flush** bu nesne sonraki dizisi noktada belirtme yönergesi.  
  
 Çünkü unutmayın **flush** yönergesi sözdizimi bir parçası olarak C dili bildirimi sahip değil, bir program içindeki yerleşimi bazı kısıtlamalar vardır. Bkz: [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) resmi dilbilgisi için. Aşağıdaki örnek, bu kısıtlamaları gösterir.  
  
```  
/* ERROR - The flush directive cannot be the immediate  
*          substatement of an if statement.  
*/  
if (x!=0)  
   #pragma omp flush (x)  
...  
  
/* OK - The flush directive is enclosed in a  
*      compound statement  
*/  
if (x!=0) {  
   #pragma omp flush (x)  
}  
```  
  
 Kısıtlamaları **flush** yönergesi aşağıdaki gibidir:  
  
-   Belirtilen değişken bir **flush** yönergesi değil bir başvuru türü olmalıdır.
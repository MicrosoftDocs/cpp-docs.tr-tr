---
title: Tür niteleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74f51dfe3b0b45fb08bc30f9b0d158275112bcf9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="type-qualifiers"></a>Tür Niteleyicileri
Tür niteleyicileri iki özelliklerden biri için tanımlayıcısını belirtin. **Const** tür niteleyicisi değiştirilemez olması için bir nesne bildirir. `volatile` Tür niteleyicisi değeri yasal olarak değiştirilebilir göründüğü, eş zamanlı yürütme iş parçacığı gibi program denetimi dışında bir şey olarak öğe bildirir.  
  
 İki tür niteleyicileri **const** ve `volatile`, bir bildirimi yalnızca bir kez görünebilir. Tür niteleyicileri hiçbir tür belirteci ile görüntülenebilir; Ancak, bunlar birden çok öğe bildiriminde ilk virgülle sonra yer alamaz. Örneğin, aşağıdaki bildirimlerini yasal şunlardır:  
  
```  
typedef volatile int VI;  
const int ci;  
```  
  
 Bu bildirimler yasal değil:  
  
```  
typedef int *i, volatile *vi;  
float f, const cf;     
```  
  
 Tür niteleyicileri yalnızca tanımlayıcıları ifadelerde l değerleri olarak erişirken ilgilidir. Bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md) l değerleri ve ifadeler hakkında bilgi için.  
  
## <a name="syntax"></a>Sözdizimi  
 *tür niteleyicisi*:  
 **constvolatile**  
  
 Aşağıdaki yasal **const** ve `volatile` bildirimleri:  
  
```  
int const *p_ci;       /* Pointer to constant int */  
int const (*p_ci);     /* Pointer to constant int */  
int *const cp_i;       /* Constant pointer to int */  
int (*const cp_i);     /* Constant pointer to int */  
int volatile vint;     /* Volatile integer        */  
```  
  
 Tür niteleyicileri bir dizi türü belirtimini içeriyorsa, öğenin nitelenmiş, dizi türü değil. İşlev türü belirtimini niteleyicileri içeriyorsa, tanımlanmamış bir davranıştır. Ne `volatile` ya da **const** değerleri aralığı ya da nesne aritmetik özelliklerini etkiler.  
  
 Bu listeyi nasıl kullanılacağını açıklar **const** ve `volatile`.  
  
-   **Const** anahtar sözcüğü, herhangi bir temel veya toplama türü veya herhangi bir türde bir nesne için bir işaretçi değiştirmek için kullanılabilir veya `typedef`. Bir öğe ile yalnızca bildirilirse **const** tür niteleyicisi türünü olmasını alınır **const Int**. A **const** değişken başlatılabilir veya bir depolama salt okunur bölgede yerleştirilebilir. **Const** anahtar sözcüğü işaretçileri bildirme için yararlıdır **const** bu işaretçiyi herhangi bir şekilde değiştirmemesi işlevi gerektirdiğinden.  
  
-   Derleyici, program herhangi bir noktada varsayar bir `volatile` değişken değerini değiştirir veya kullanan bilinmeyen bir işlem tarafından erişilebilir. Bu nedenle, komutunda belirtilen iyileştirmeler bakılmaksızın satır, her bir atama için kod veya, başvuru bir `volatile` etkisinin için görünse bile değişkeni oluşturulmalıdır.  
  
     Varsa `volatile` kullandığınızda, tek başına kullanılan `int` varsayılır. `volatile` Tür belirteci, özel bir bellek konumuna güvenilir erişim sağlamak için kullanılabilir. Kullanım `volatile` g/ç denetim eşzamanlı olarak yürütülen programlara veya gibi bellek eşlemeli özel bir donanım tarafından erişilen veya sinyal işleyiciler tarafından değiştirilmiş olabilir veri nesneleri ile kaydeder. Bir değişken olarak bildirebilir `volatile` yaşam süresi veya olacak şekilde tek bir başvuru çevirebilirsiniz için `volatile`.  
  
-   Öğenin her ikisi de olabilir **const** ve `volatile`, bu durumda öğe kendi program tarafından yasal olarak değiştirilemedi, ancak bazı zaman uyumsuz bir işlem tarafından değiştirilmiş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Türler](../c-language/declarations-and-types.md)
---
title: "Yöneltmesi ve adresi işleçlerin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- address-of operator (&)
- '* operator'
- operators [C++], address-of
- ampersand operator (&)
- '* operator, indirection operator'
- addresses [C++], indirection
- addresses [C++]
- indirection operator
- '& operator, address-of operator'
- null pointers [C++]
- '* operator, address-of operator'
- operators [C++], indirection
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 85d2510658bdf534f25ccc3efc29c88da1c93eff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="indirection-and-address-of-operators"></a>İşleçlerin Yöneltmesi ve Adresi
İndirection işleci (**\***) bir değer bir işaretçi dolaylı olarak erişir. İşlenen, bir işaretçi değeri olmalıdır. İşlemin sonucu, işlenen tarafından ele alınan değerdir; yani işlenenin işaret ettiği adresteki değerdir. Sonucun türü, işlenenin ele aldığı türdür.  
  
 İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir depolama konumuna işaret ediyorsa, sonuç depolama konumunu gösteren l değeridir.  
  
 İşaretçi değeri geçersiz, tanımlanmamış bir sonucudur. Aşağıdaki liste, işaretçi değerini geçersiz kılan en yaygın koşulların bazılarını içermektedir.  
  
-   İşaretçi, bir null işaretçidir.  
  
-   İşaretçi, başvuru sırasında görünür olmayan yerel bir öğrenin adresini belirtir.  
  
-   İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.  
  
-   İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.  
  
 Address-of işleci (**&**), işlenen adresini verir. Address-of işleci işleneni işlevi Belirleyicisi ya da bir bit alanı değildir ve ile bildirilmemiş bir nesne atayan bir l-değeri olabilir **kaydetmek** depolama sınıfı tanımlayıcısı.  
  
 Adres işleneninin sonucu, işlenenin işaretçisidir. İşaretçi tarafından ele alınan tür, işleneninin türüdür.  
  
 Adres işleci, yalnızca temel, yapı veya birleşim türlerindeki dosya kapsamı düzeyinde bildirilen değişkenlere veya alt simgeli dizi başvurularına uygulanabilir. Bu ifadelerde, adres işlecini içermeyen sabit bir ifade adres ifadesine eklenebilir veya bu ifadeden çıkarılabilir.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örnekler bu bildirimleri kullanır:  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 Bu deyim, adres işlecini kullanır:  
  
```  
pa = &a[5];  
```  
  
 Address-of işleci (**&**) dizisinin altıncı öğesi adresini alır `a`. Sonuç, `pa` işaretçi değişkeninde depolanır.  
  
```  
x = *pa;  
```  
  
 İndirection işleci (**\***) erişmek için bu örnekte kullanılan `int` depolanan adresi değerinde `pa`. Değer, `x` tamsayı değişkenine atanır.  
  
```  
if( x == *&x )  
    printf( "True\n" );  
```  
  
 Bu örnekte, `True` sözcüğü yazdırılarak yöneltme işlecinin `x` adresine uygulanmasıyla elde edilen sonucun `x` ile aynı olduğu gösterilir.  
  
```  
int roundup( void );     /* Function declaration */  
  
int  *proundup  = roundup;  
int  *pround  = &roundup;  
```  
  
 `roundup` işlevi bildirildiğinde, iki `roundup` işaretçisi bildirilir ve başlatılır. İlk işaretçi `proundup` yalnızca işlevin adı kullanılarak başlatılır, ikinci işaretçi `pround` ise başlatma sırasında adres işlecini kullanır. Başlatma işlemleri eşdeğerdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönlendirme işleci: *](../cpp/indirection-operator-star.md)   
 [Address-of işleci: &](../cpp/address-of-operator-amp.md)
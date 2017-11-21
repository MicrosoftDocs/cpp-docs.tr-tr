---
title: "C tür tanımlayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 78cd6292c97f41cb7e862389113404346da80460
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-type-specifiers"></a>C Tür Tanımlayıcıları
Tür tanımlayıcıları bildirimlerden bir değişken veya işlev bildirimi türünü tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
 *tür belirteci*:  
 **void**  
  
 **char**  
  
 **kısa**  
  
 **int**  
  
 **uzun**  
  
 **kayan nokta**  
  
 **çift**  
  
 **İmzalı**  
  
 **İmzasız**  
  
 *yapı veya birleşim belirticisi*  
  
 *Liste belirticisi*  
  
 *TypeDef adı*  
  
 **Char imzalı**, **imzalı int**, **imzalı short int**, ve **imzalı long int** türleri ile birlikte bunların `unsigned` ortaklarınıza ve `enum`, "tam sayı" türleri olarak adlandırılır. **Float**, **çift**, ve `long double` tür tanımlayıcıları "kayan" veya "kayan nokta" türleri olarak adlandırılır. Tam sayı veya kayan nokta türü belirleyici bir değişken ya da işlevi bildiriminde kullanabilirsiniz. Varsa bir *tür belirteci* sağlanmaz bir bildiriminde gerçekleştirilecek olmasını `int`.  
  
 İsteğe bağlı anahtar sözcükleri **imzalı** ve `unsigned` önünde veya tam sayı türlerinden herhangi birini dışında izleyin `enum`ve ayrıca tek başına kullanılabilir tür tanımlayıcıları, bu durumda bunlar olarak anlaşılır **imzalı int**  ve `unsigned int`sırasıyla. Tek başına, anahtar sözcüğü kullanıldığında `int` varsayılır **imzalı**. Tek başına, anahtar sözcükler kullanıldığında **uzun** ve **kısa** olarak anladım **uzun tamsayı** ve `short int`.  
  
 Numaralandırma türleri temel türleri olarak kabul edilir. Numaralandırma türleri için tür tanımlayıcıları içinde ele alınmıştır [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md).  
  
 Anahtar sözcüğü `void` üç kullanımı vardır: bir işlevin dönüş türü, bağımsız değişken almayan bir işlev için bir bağımsız değişken türü listesi belirtin ve belirtilmeyen bir türü için bir işaretçi belirtmek için belirtmek için. Kullanabileceğiniz `void` türü herhangi bir değer döndüren işlevler bildirmek için veya belirtilmeyen bir türü için bir işaretçi bildirmek için. Bkz: [bağımsız değişkenleri](../c-language/arguments.md) hakkında bilgi için `void` zaman göründüğü işlevi adından parantez içinde tek başına.  
  
 **Microsoft özel**  
  
 Türü olup olmadığı denetleniyor şimdi ANSI türü anlamı uyumlu, **kısa** ve türü `int` ayrı türleridir. Örneğin, yeniden tanımlama Derleyici önceki sürümleri tarafından kabul edildi Microsoft C Derleyici de budur.  
  
```  
int   myfunc();  
short myfunc();  
```  
  
 Sonraki Bu örnek ayrıca farklı yöneltme hakkında bir uyarı üretir:  
  
```  
int *pi;  
short *ps;  
  
ps = pi;  /* Now generates warning */  
```  
  
 Microsoft C derleyicisi ayrıca oturum farklılıkları için uyarılar oluşturur. Örneğin:  
  
```  
signed int *pi;  
unsigned int *pu  
  
pi = pu;  /* Now generates warning */  
```  
  
 Tür `void` ifadeleri yan etkileri için değerlendirilir. Türüne sahip bir ifade (var olmayan) değeri kullanamazsınız `void` hiçbir şekilde ya da can dönüştürdüğünüz içinde bir `void` ifadeyle (örtük veya açık dönüştürme) dışında herhangi bir tür için `void`. Diğer bir türü bir ifadenin bir bağlamda kullanıyorsanız burada bir `void` ifade gereklidir, değeri göz ardı edilir.  
  
 ANSI belirtimine uygun olarak **void\* \***  olarak kullanılamaz **int\*\***. Yalnızca **void\***  belirtilmeyen bir türü için bir işaretçi olarak kullanılabilir.  
  
 **SON Microsoft özel**  
  
 Ek tür tanımlayıcıları ile oluşturabileceğiniz `typedef` açıklandığı gibi bildirimleri [Typedef bildirimleri](../c-language/typedef-declarations.md). Bkz: [temel türleri depolama](../c-language/storage-of-basic-types.md) boyutu bilgi her tür için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve türler](../c-language/declarations-and-types.md)
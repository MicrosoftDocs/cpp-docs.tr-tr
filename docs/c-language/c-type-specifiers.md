---
title: C tür tanımlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e37ac421627d4c4503d75eaf65188bbe234af015
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-type-specifiers"></a>C Tür Tanımlayıcıları

Tür tanımlayıcıları bildirimlerden bir değişken veya işlev bildirimi türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

*tür belirteci*:  
&nbsp;&nbsp;**Geçersiz kılma**  
&nbsp;&nbsp;**char**  
&nbsp;&nbsp;**kısa**  
&nbsp;&nbsp;**Int**  
&nbsp;&nbsp;**uzun**  
&nbsp;&nbsp;**Kayan nokta**  
&nbsp;&nbsp;**Çift**  
&nbsp;&nbsp;**İmzalı**  
&nbsp;&nbsp;**İmzasız**  
&nbsp;&nbsp;*yapı veya birleşim belirticisi*  
&nbsp;&nbsp;*Liste belirticisi*  
&nbsp;&nbsp;*TypeDef adı*  

**Char imzalı**, **imzalı int**, **imzalı short int**, ve **imzalı long int** türleri ile birlikte bunların **imzalanmamış**  ortaklarınıza ve **enum**, denir *tam sayı* türleri. **Float**, **çift**, ve **uzun çift** tür tanımlayıcıları denir *kayan* veya *kayan nokta* türleri. Tam sayı veya kayan nokta türü belirleyici bir değişken ya da işlevi bildiriminde kullanabilirsiniz. Varsa bir *tür belirteci* sağlanmaz bir bildiriminde gerçekleştirilecek olmasını **int**.

İsteğe bağlı anahtar sözcükleri **imzalı** ve **imzasız** önünde veya tam sayı türlerinden herhangi birini dışında izleyin **enum**ve ayrıca kullanılabilir durumda tür tanımlayıcıları olarak tek başına olarak anladım **imzalı int** ve **imzasız int**sırasıyla. Tek başına, anahtar sözcüğü kullanıldığında **int** varsayılır **imzalı**. Tek başına, anahtar sözcükler kullanıldığında **uzun** ve **kısa** olarak anladım **uzun tamsayı** ve **short int**.

Numaralandırma türleri temel türleri olarak kabul edilir. Numaralandırma türleri için tür tanımlayıcıları içinde ele alınmıştır [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md).

Anahtar sözcüğü **void** üç kullanımı vardır: bir işlevin dönüş türü, bağımsız değişken almayan bir işlev için bir bağımsız değişken türü listesi belirtin ve belirtilmeyen bir türü için bir işaretçi belirtmek için belirtmek için. Kullanabileceğiniz **void** türü herhangi bir değer döndüren işlevler bildirmek için veya belirtilmeyen bir türü için bir işaretçi bildirmek için. Bkz: [bağımsız değişkenleri](../c-language/arguments.md) hakkında bilgi için **void** zaman göründüğü işlevi adından parantez içinde tek başına.

**Microsoft özel**

Türü olup olmadığı denetleniyor şimdi ANSI türü anlamı uyumlu, **kısa** ve türü **int** ayrı türleridir. Örneğin, yeniden tanımlama Derleyici önceki sürümleri tarafından kabul edildi Microsoft C Derleyici de budur.

```C
int   myfunc();
short myfunc();
```

Sonraki Bu örnek ayrıca farklı yöneltme hakkında bir uyarı üretir:

```C
int *pi;
short *ps;

ps = pi;  /* Now generates warning */
```

Microsoft C derleyicisi ayrıca oturum farklılıkları için uyarılar oluşturur. Örneğin:

```C
signed int *pi;
unsigned int *pu

pi = pu;  /* Now generates warning */
```

Tür **void** ifadeleri yan etkileri için değerlendirilir. Türüne sahip bir ifade (var olmayan) değeri kullanamazsınız **void** hiçbir şekilde ya da can dönüştürdüğünüz içinde bir **void** ifadeyle (örtük veya açık dönüştürme) dışında herhangi bir tür için **void** . Diğer bir türü bir ifadenin bir bağlamda kullanıyorsanız burada bir **void** ifade gereklidir, değeri göz ardı edilir.

ANSI belirtimine uygun olarak **void\* \***  olarak kullanılamaz **int\*\***. Yalnızca **void\***  belirtilmeyen bir türü için bir işaretçi olarak kullanılabilir.

**SON Microsoft özel**

Ek tür tanımlayıcıları ile oluşturabileceğiniz **typedef** açıklandığı gibi bildirimleri [Typedef bildirimleri](../c-language/typedef-declarations.md). Bkz: [temel türleri depolama](../c-language/storage-of-basic-types.md) boyutu bilgi her tür için.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)  

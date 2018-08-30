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
ms.openlocfilehash: f965481ae1d3abea40577680b1af72004f793123
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197234"
---
# <a name="c-type-specifiers"></a>C Tür Tanımlayıcıları

Tür belirleyicilerde bildirimleri bir değişken veya işlev bildirimi türünü tanımlayın.

## <a name="syntax"></a>Sözdizimi

*tür belirticisi*:  
&nbsp;&nbsp;**Geçersiz kılma**  
&nbsp;&nbsp;**Char**  
&nbsp;&nbsp;**kısa**  
&nbsp;&nbsp;**int**  
&nbsp;&nbsp;**uzun**  
&nbsp;&nbsp;**kayan nokta**  
&nbsp;&nbsp;**çift**  
&nbsp;&nbsp;**İmzalı**  
&nbsp;&nbsp;**İşaretsiz**  
&nbsp;&nbsp;*struct veya union tanımlayıcısı*  
&nbsp;&nbsp;*sabit listesi belirticisi*  
&nbsp;&nbsp;*TypeDef adı*  

**Signed char**, **signed int**, **imzalı short int**, ve **imzalı long int** türleri ile birlikte bunların **işaretsiz**  ortaklarınıza ve **enum**, adlandırılır *integral* türleri. **Float**, **çift**, ve **uzun çift** tür tanımlayıcıları denir *kayan* veya *kayan nokta* türleri. Herhangi bir tamsayı veya kayan nokta türü belirticisi, bir değişken veya işlev bildiriminde kullanabilirsiniz. Varsa bir *tür tanımlayıcısı* sağlanmamış bir bildiriminde olmasını alınır **int**.

İsteğe bağlı anahtar sözcük **imzalı** ve **işaretsiz** önünde veya tam sayı türlerinden herhangi birini dışında izleyin **enum**ve ayrıca kullanılabilir durumda tür tanımlayıcıları olarak tek başına olarak anlaşılmasını **signed int** ve **işaretsiz int**sırasıyla. Tek başına, anahtar sözcüğü kullanıldığında **int** varsayılır **imzalı**. Tek başına, anahtar sözcükleri kullanıldığında **uzun** ve **kısa** olarak anlaşılabilir **long int** ve **kısa tamsayı**.

Numaralandırma türleri, temel türler olarak kabul edilir. Numaralandırma türleri için tür tanımlayıcıları açıklanmıştır [numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md).

Anahtar sözcüğü **void** üç kullanımı vardır: bir işlev dönüş türü, bir bağımsız değişken alan bir işlev için bağımsız değişken türü listesi belirtin ve belirtilmeyen bir türün işaretçisine belirtmek için belirtmek için. Kullanabileceğiniz **void** türü herhangi bir değer döndüren işlevleri bildirin veya belirtilmeyen bir türün işaretçisine bildirmek için. Bkz: [bağımsız değişkenleri](../c-language/arguments.md) hakkında bilgi için **void** zaman göründüğü bir işlev adının parantez içinde tek başına.

**Microsoft'a özgü**

Tür denetleme, artık ANSI türü diğer bir deyişle uyumlu, **kısa** ve türü **int** ayrı türleridir. Örneğin, bir önceki derleyici sürümleri tarafından kabul edilen Microsoft C derleyicisi yeniden tanımlama budur.

```C
int   myfunc();
short myfunc();
```

Bu örnekte, aynı zamanda farklı türleri için yöneltme hakkında bir uyarı oluşturur:

```C
int *pi;
short *ps;

ps = pi;  /* Now generates warning */
```

Microsoft C derleyicisi, aynı zamanda oturum farklılıkları için uyarılar oluşturur. Örneğin:

```C
signed int *pi;
unsigned int *pu

pi = pu;  /* Now generates warning */
```

Tür **void** ifadelerin yan etkileri için değerlendirilir. (Var olmayan) bir değer türüne sahip ifade kullanılamaz **void** hiçbir yolu ya da can dönüştürmeniz de bir **void** ifadesiyle (örtük veya açık dönüştürme) dışında herhangi bir tür için **void** . Diğer türdeki bir ifade bir bağlamda kullanıyorsanız burada bir **void** ifade gereklidir, değeri atılır.

ANSI belirtime uygun <strong>void\* \*</strong>  olarak kullanılamaz <strong>int\*\*</strong>. Yalnızca **void** <strong>\*</strong> belirtilmeyen bir türün işaretçisi olarak kullanılabilir.

**END Microsoft özgü**

Ek tür tanımlayıcıları ile oluşturabileceğiniz **typedef** açıklandığı bildirimleri [Typedef bildirimleri](../c-language/typedef-declarations.md). Bkz: [temel türlerin depolanması](../c-language/storage-of-basic-types.md) her türün boyut hakkında bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)  

---
title: C Tür Tanımlayıcıları
ms.date: 01/29/2018
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
ms.openlocfilehash: 652388fdf345cab7878bbd8c054b769377b322a9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217161"
---
# <a name="c-type-specifiers"></a>C Tür Tanımlayıcıları

Bildirimlerinde tür belirticileri bir değişken veya işlev bildiriminin türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

*tür belirleyicisi*: &nbsp; &nbsp; &nbsp; &nbsp; **`void`** &nbsp; &nbsp; &nbsp; &nbsp; **`char`** &nbsp; &nbsp; &nbsp; &nbsp; **`short`** &nbsp; &nbsp; &nbsp; &nbsp; **`int`** &nbsp; &nbsp; &nbsp; &nbsp; **`long`** &nbsp; &nbsp; &nbsp; &nbsp; **`float`** &nbsp; &nbsp; &nbsp; &nbsp; **`double`** &nbsp; &nbsp; &nbsp; &nbsp; **`signed`** &nbsp; &nbsp; &nbsp; &nbsp; **`unsigned`** &nbsp; &nbsp; &nbsp; &nbsp; *struct-or-Union-belirleyicisi* &nbsp; &nbsp; &nbsp; &nbsp; *enum-belirleyicisi* &nbsp; &nbsp; &nbsp; &nbsp; *typedef-Name*

**`signed char`**,, **`signed int`** **`signed short int`** Ve **imzalı uzun int** türleri, **`unsigned`** karşılıklarıyla birlikte ve **`enum`** , *integral* türler olarak adlandırılır. **`float`**, **`double`** Ve **`long double`** tür belirticileri *kayan* veya *kayan nokta* türleri olarak adlandırılır. Bir değişken veya işlev bildiriminde, herhangi bir integral veya kayan nokta tür belirleyicisi kullanabilirsiniz. Bir bildirimde bir *tür belirleyicisi* sağlanmazsa, bu, olarak alınır **`int`** .

İsteğe bağlı anahtar sözcükler **`signed`** ve, **`unsigned`** hariç olmak üzere tüm integral türlerini kullanabilir ya da izleyebilir, **`enum`** ve sırasıyla tür belirticileri olarak de kullanılabilir ve bu durumda, sırasıyla ve olarak anlaşılabilirler **`signed int`** **`unsigned int`** . Tek başına kullanıldığında, anahtar sözcüğünün olduğu **`int`** varsayılır **`signed`** . Tek başına kullanıldığında, anahtar sözcükler **`long`** ve **`short`** **long int** ve olarak anlaşılmıştır **`short int`** .

Sabit listesi türleri temel türler olarak değerlendirilir. Numaralandırma türleri için tür belirticileri, [numaralandırma bildirimlerinde](../c-language/c-enumeration-declarations.md)ele alınmıştır.

Anahtar sözcüğünün **`void`** üç kullanımı vardır: bir işlev dönüş türü belirtmek için, bağımsız değişken içermeyen bir işlev için bağımsız değişken türü listesi belirtmek ve belirtilmemiş bir tür işaretçisi belirtmek için. **`void`** Türü, hiçbir değer döndürmeyen veya belirtilmemiş bir türe işaretçi bildiren işlevleri bildirmek için kullanabilirsiniz. [Arguments](../c-language/arguments.md) **`void`** Bir işlev adından sonra parantez içinde tek tek göründüğü hakkında bilgi Için bkz. bağımsız değişkenler.

**Microsoft'a Özgü**

Tür denetlemesi artık ANSI uyumludur, bu da tür **`short`** ve tür **`int`** farklı türlerdir. Örneğin, bu, derleyicinin önceki sürümleri tarafından kabul edilen Microsoft C derleyicisinde yeniden tanımlama.

```C
int   myfunc();
short myfunc();
```

Bu sonraki örnek ayrıca farklı türlere yöneltme hakkında bir uyarı oluşturur:

```C
int *pi;
short *ps;

ps = pi;  /* Now generates warning */
```

Microsoft C derleyicisi Ayrıca, oturum açma farkları için uyarılar üretir. Örnek:

```C
signed int *pi;
unsigned int *pu

pi = pu;  /* Now generates warning */
```

Tür **`void`** ifadeleri yan etkilere göre değerlendirilir. Herhangi bir şekilde türü olan bir ifadenin (varolmayan) değerini kullanamazsınız **`void`** , ya da bir **`void`** ifadeyi (örtük veya açık dönüştürmeye) dışında herhangi bir türe dönüştürebilirsiniz **`void`** . Bir ifadenin gerekli olduğu bir bağlamda başka herhangi bir türün ifadesini kullanırsanız **`void`** , değeri atılır.

ANSI belirtimine uymak için, <strong>void \* \* </strong> <strong>int \* \* </strong>olarak kullanılamaz. Yalnızca **`void`** <strong>\*</strong> belirtilmeyen bir tür için işaretçi olarak kullanılabilir.

**SON Microsoft 'a özgü**

**`typedef`** [Typedef bildirimleri](../c-language/typedef-declarations.md)bölümünde açıklandığı gibi bildirimlerle ek tür belirticileri oluşturabilirsiniz. Her türün boyutu hakkında bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)

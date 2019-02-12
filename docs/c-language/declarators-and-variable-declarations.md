---
title: Bildirimler ve Değişken Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- declaring variables, declarators
- declarators, definition
- declaring variables, declaration statements
ms.assetid: 5fd67a6a-3a6a-4ec9-b257-3f7390a48d40
ms.openlocfilehash: 928de4b1724577a9fdb282f5109b4b5d0b31c4e6
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147496"
---
# <a name="declarators-and-variable-declarations"></a>Bildirimler ve Değişken Bildirimleri

Bu bölümün geri kalanında, form ve bildirimleri bu listede özetlenen değişken türleri için anlamı açıklanmaktadır. Özellikle, kalan bölümler aşağıdaki bildirmek açıklanmaktadır:

|Değişken türü|Açıklama|
|----------------------|-----------------|
|[Basit değişkenler](../c-language/simple-variable-declarations.md)|Tamsayı veya kayan nokta türü tek değerli değişkenlerle|
|[Diziler](../c-language/array-declarations.md)|Değişkenler aynı türde öğe koleksiyonunu oluşur|
|[İşaretçiler](../c-language/pointer-declarations.md)|Diğer değişkenleri ve değerler yerine (adresleri biçiminde) değişken konumlarını içeren değişkenleri|
|[Sabit listesi değişkenleri](../c-language/c-enumeration-declarations.md)|Bir dizi adlandırılmış tamsayı sabitlerini, tutulan bir değerden integral ile basit değişken türü|
|[Yapılar](../c-language/structure-declarations.md)|Değişkenleri farklı türlere sahip olabilen değerlerin koleksiyonunu oluşur.|
|[Birleşimler](../c-language/union-declarations.md)|Aynı depolama alanı kaplayabilir farklı türlerde birden fazla değerlerinden oluşan değişkenleri|

Bir bildirimci programa tanıtılmak üzere adını belirten bir bildirim parçasıdır. Değiştiriciler gibi içerebilir <strong>\*</strong> (işaretçi-için) ve Microsoft çağırma kuralı anahtar sözcükler.

**Microsoft'a özgü**

Bildiricide

```C
__declspec(thread) char *var;
```

`char` türü belirleyici `__declspec(thread)` ve `*` değiştiricilerdir ve `var` tanımlayıcının adı.

**END Microsoft özgü**

Bildirimciler, değer, değerleri ve belirtilen bir tür değerleri döndüren işlev işaretçileri dizilerini bildirmek için kullanın. Daha sonra bu bölümde açıklanan dizisi ve işaretçi bildirimleri Bildirimciler görünür.

## <a name="syntax"></a>Sözdizimi

*bildirimci*:<br/>
&nbsp;&nbsp;*İşaretçi*<sub>iyileştirilmiş</sub> *doğrudan bildirimcisi*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(***bildirimci***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci***[***sabit-ifade*<sub>iyileştirilmiş</sub> **]** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci***(***parametre türü listesi***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*doğrudan bildirimci***(***tanımlayıcı listesi*<sub>iyileştirilmiş</sub> **)**

*İşaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyici listesi*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *tür niteleyici listesi*<sub>iyileştirilmiş</sub> *işaretçi*

*tür niteleyici listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyici listesi tür niteleyicisi*

> [!NOTE]
> Söz dizimi için bkz *bildirimi* içinde [genel bakış, bildirimleri](../c-language/overview-of-declarations.md) veya [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md) başvuran söz dizimi bir *bildirimci*.

Bir bildirimci değiştirilmemiş bir tanımlayıcı oluşuyorsa, bildirilen öğenin bir taban türü vardır. Yıldız işareti (<strong>\*</strong>) türü bir işaretçi türüne değiştiren bir tanımlayıcının sola görünür. Tanımlayıcı köşeli parantez izlediyseniz (**[]**), türü bir dizi türü için değiştirilir. Tanımlayıcı parantezle izlediyseniz, türü bir işlev türü için değiştirildi. Öncelik bildirimleri içinde yorumlama hakkında daha fazla bilgi için bkz. [daha karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md).

Her bildirimci en az bir tanımlayıcı bildirir. Bir bildirimci, tam bir bildirim olması için bir tür tanımlayıcısı içermelidir. Tür belirticisi, bir dizi türü, bir işaretçi türü tarafından ele alınan nesnenin türü veya bir işlevin dönüş türünü öğelerin türü sunar.

[Dizi](../c-language/array-declarations.md) ve [işaretçi](../c-language/pointer-declarations.md) bildirimleri, bu bölümün ileriki kısımlarında daha ayrıntılı açıklanmıştır. Aşağıdaki örnekler birkaç basit tür bildirimcileri gösterir:

```C
int list[20]; // Declares an array of 20 int values named list
char *cp;     // Declares a pointer to a char value
double func( void ); // Declares a function named func, with no
                     // arguments, that returns a double value
int *aptr[10] // Declares an array of 10 pointers
```

**Microsoft'a özgü**

Microsoft C derleyicisi bir aritmetik, yapı veya birleşim türü değiştirebilirsiniz Bildirimciler sayısını sınırlamaz. Sayı yalnızca kullanılabilir bellekle sınırlıdır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)

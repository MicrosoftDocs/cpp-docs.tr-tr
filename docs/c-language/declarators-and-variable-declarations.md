---
title: Bildirimler ve Değişken Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- declaring variables, declarators
- declarators, definition
- declaring variables, declaration statements
ms.assetid: 5fd67a6a-3a6a-4ec9-b257-3f7390a48d40
ms.openlocfilehash: 928de4b1724577a9fdb282f5109b4b5d0b31c4e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234536"
---
# <a name="declarators-and-variable-declarations"></a>Bildirimler ve Değişken Bildirimleri

Bu bölümün geri kalanında, bu listede özetlenen değişken türleri için bildirimlerin biçimi ve anlamı açıklanmaktadır. Özellikle, geri kalan bölümlerde aşağıdakilerin nasıl bildirileceğini açıklanmaktadır:

|Değişken türü|Açıklama|
|----------------------|-----------------|
|[Basit değişkenler](../c-language/simple-variable-declarations.md)|İntegral veya kayan nokta türünde tek değerli değişkenler|
|[Diziler](../c-language/array-declarations.md)|Aynı türdeki bir öğe koleksiyonundan oluşan değişkenler|
|[İşaretçiler](../c-language/pointer-declarations.md)|Diğer değişkenlere işaret eden ve değerler yerine değişken konumları (adresler biçiminde) içeren değişkenler|
|[Sabit Listesi değişkenleri](../c-language/c-enumeration-declarations.md)|Bir adlandırılmış tamsayı sabitleri kümesinden bir değer tutan integral türü olan basit değişkenler|
|[Yapılar](../c-language/structure-declarations.md)|Farklı türlere sahip bir değer koleksiyonundan oluşan değişkenler|
|[Birleşimler](../c-language/union-declarations.md)|Aynı depolama alanını kaplayan farklı türlerin çeşitli değerlerinden oluşan değişkenler|

Bildirimci, programın programa tanıtılme adını belirten bir bildirimin parçasıdır. <strong>\*</strong> (İşaretçi) gibi değiştiriciler ve herhangi bir Microsoft çağırma kuralı anahtar kelimeleriyle bulunabilir.

**Microsoft'a Özgü**

Bildirimci içinde

```C
__declspec(thread) char *var;
```

`char`tür belirticisidir `__declspec(thread)` ve `*` değiştiriciler olur ve `var` tanımlayıcı adıdır.

**SON Microsoft 'a özgü**

Değerlerin dizilerini, değerlerin işaretçilerini ve belirli bir türün değerlerini döndüren işlevleri bildirmek için Bildirimciler kullanırsınız. Bildiriciler, bu bölümün ilerleyen kısımlarında açıklanan dizi ve işaretçi bildirimlerinde görüntülenir.

## <a name="syntax"></a>Sözdizimi

*bildirimci*:<br/>
&nbsp;&nbsp;*işaretçi*<sub>opt</sub> *doğrudan bildirimci*

*doğrudan bildirimci*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(**  *bildirimci*  **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator*  **[**  *sabit ifade*<sub>katılımı</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator*  **(**  *parametre-tür-listesi*  **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Direct-declarator*  **(**  *tanımlayıcı listesi*<sub>opt</sub> **)**

*işaretçi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong>*tür niteleyicisi-List*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong>*tür niteleyicisi-liste*<sub>opt</sub> *işaretçisi*

*tür niteleyicisi-Listele*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi-liste tür niteleyicisi*

> [!NOTE]
> *Bildirimci*'e başvuran sözdizimi için bildirimlere veya [C dili sözdizimi özetine](../c-language/c-language-syntax-summary.md) [genel bakış](../c-language/overview-of-declarations.md) bölümünde *bildirime* ilişkin sözdizimine bakın.

Bir bildirimci, değiştirilmemiş bir tanımlayıcıdan oluşuyorsa, bildirildiği öğenin bir temel türü vardır. Bir tanımlayıcının solunda bir<strong>\*</strong>yıldız işareti () görünürse, tür bir işaretçi türüne değiştirilir. Tanımlayıcının ardından köşeli ayraç (**[]**) varsa, tür bir dizi türüne değiştirilir. Tanımlayıcının arkasından parantez varsa, tür bir işlev türüne değiştirilir. Bildirimler içindeki önceliği yorumlama hakkında daha fazla bilgi için bkz. [daha karmaşık Bildirimcileri Yorumlama](../c-language/interpreting-more-complex-declarators.md).

Her bildirimci en az bir tanımlayıcı bildirir. Bir bildirimci, bir tür belirleyicisi içermelidir ve bu bir bildirimin tamamını içerir. Tür Belirleyicisi, bir dizi türünün öğelerinin türüne, bir işaretçi türü tarafından belirtilen nesne türüne veya bir işlevin dönüş türüne sahiptir.

[Dizi](../c-language/array-declarations.md) ve [işaretçi](../c-language/pointer-declarations.md) bildirimleri bu bölümün ilerleyen kısımlarında daha ayrıntılı bir şekilde ele alınmıştır. Aşağıdaki örneklerde bazı bildirimcilerin birkaç basit biçimi gösterilmektedir:

```C
int list[20]; // Declares an array of 20 int values named list
char *cp;     // Declares a pointer to a char value
double func( void ); // Declares a function named func, with no
                     // arguments, that returns a double value
int *aptr[10] // Declares an array of 10 pointers
```

**Microsoft'a Özgü**

Microsoft C derleyicisi, bir aritmetik, yapı veya birleşim türünü değiştirebilen bildirimcilerin sayısını sınırlamaz. Numara yalnızca kullanılabilir bellekle sınırlıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)

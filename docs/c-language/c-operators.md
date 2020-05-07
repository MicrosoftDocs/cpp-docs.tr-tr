---
title: C İşleçleri
ms.date: 06/14/2018
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
ms.openlocfilehash: 139eedf54ab42ddc34b5c049abfcd1c2638c5efc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326384"
---
# <a name="c-operators"></a>C İşleçleri

C işleçleri, [C++ yerleşik işleçlerinin](../cpp/cpp-built-in-operators-precedence-and-associativity.md)bir alt kümesidir.

Üç tür işleç vardır. Birli ifade, bir işlenenden bir birli işleç önüne veya bir ifadenin ardından **sizeof** anahtar sözcüğünü içerir. İfade, değişkenin adı veya atama ifadesi olabilir. İfade atama ifadesiyse, parantez içine alınmalıdır. İkili ifade, ikili işleç tarafından birleştirilmiş iki işlenenden oluşur. Üçlü ifade, koşullu ifade işleci tarafından birleştirilmiş üç işlenenden oluşur.

C, aşağıdaki tekli işleçler içerir:

|Sembol|Name|
|------------|----------|
|**-** **~** **!**|Olumsuzlaştırma ve tamamlayıcı işleçleri|
|**&#42;****&**|Yöneltme ve adres işleçleri|
|**sizeof**|Boyut işleci|
|**+**|Tekli artı işleci|
|**++** **--**|Tekli artırma ve azaltma işleçleri|

Soldan sağa ilişkilendirilen ikili işleçler. C, aşağıdaki ikili işleçleri sağlar:

|Sembol|Name|
|------------|----------|
|**&#42;** **/****%**|Çarpma işleçleri|
|**+** **-**|Toplama işleçleri|
|**\<\<** **>>**|Kaydırma işleçleri|
|**\<****>** **\<** **>=** **==** **!=**|İlişkisel işleçler|
|**&****&#124;****^**|Bit düzeyinde işleçler|
|**&&****&#124;&#124;**|Mantıksal işleçler|
|**,**|Sıralı değerlendirme işleci|

Microsoft 16 bit C derleyicisi 'nin önceki sürümleri tarafından desteklenen temel işleç (**: >**), [C dili sözdizimi özetinde](../c-language/c-language-syntax-summary.md)açıklanmıştır.

Koşullu ifade işleci, ikili ifadelere göre daha düşük önceliğe sahiptir ve sağla ilişkilendirilebilir olduğu için onlardan farklıdır.

İşleçlere sahip ifadeler, tekli veya ikili atama işleçleri kullanan atama ifadeleri de içerir. Birli atama işleçleri, artırma (**++**) ve azaltma (**--**) işleçleridir; ikili atama işleçleri basit atama işleçtir (**=**) ve bileşik atama işleçleridir. Her bileşik atama işleci, başka bir ikili işlecin basit atama işleciyle birleşiminden oluşur.

## <a name="see-also"></a>Ayrıca bkz.

- [İfadeler ve atamalar](../c-language/expressions-and-assignments.md)

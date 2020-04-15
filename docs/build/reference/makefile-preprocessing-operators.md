---
title: Derleme Görevleri Dosyası Önişleme İşleçleri
ms.date: 06/14/2018
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
ms.openlocfilehash: 212f39ee62008b391977aaa91d5c8c4fadfd9730
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336466"
---
# <a name="makefile-preprocessing-operators"></a>Derleme Görevleri Dosyası Önişleme İşleçleri

Makefile ön işleme ifadeleri sabit değerler, komutlardan çıkış kodları, dizeleri, makrolar ve dosya sistemi yolları üzerinde hareket operatörleri kullanabilirsiniz. İfadeyi değerlendirmek için, önişlemci önce makroları genişletir, sonra komutları yürütür ve sonra işlemleri gerçekleştirir. İşlemler parantez içinde açık gruplandırma sırasına göre ve daha sonra işleç önceliği sırasına göre değerlendirilir. Sonuç sabit bir değerdir.

**DEFINED** işleci, makro adı üzerinde hareket eden mantıksal bir işleçtir. Makroname tanımlanırsa, atanmış bir *macroname* değeri olmasa bile DEFINED _(makroname)_**)** ifadesi doğrudur. **DEFINED(** Ile birlikte **DEFINED** **! IF** veya **! ELSE IF** eşdeğerdir **! IFDEF** veya **! ELSE IFDEF**. Ancak, bu yönergelerin aksine, **DEFINED** karmaşık ifadelerde kullanılabilir.

**EXIST** işleci, dosya sistemi yolunda hareket eden mantıksal bir işleçtir. Eğer *yol* varsa VAR _(yol)_**)** doğrudur. **EXIST(** **EXIST'in** sonucu ikili ifadelerde kullanılabilir. *Yol* boşluklar içeriyorsa, çift tırnak işaretlerine biçine alıkonun.

İki dizeyi karşılaştırmak için**==** eşitlik ( ) işleci veya eşitsizlik (**!=**) işleci kullanın. Dizeleri çift tırnak işaretlerine ekin.

İnteger sabitleri sayısal olumsuzlama (**-**), kişinin tamamlayıcısı (**~**), ve mantıksal olumsuzlama (**!**) için unary işleçleri kullanabilirsiniz.

İfadeler aşağıdaki işleçleri kullanabilir. Eşit önceliğe göre işleçler birlikte gruplandırılır ve gruplar azalan öncelik sırasına göre listelenir. Unary operatörler sağ operand ile ilişkilendirmek. Eşit önceliğe bağlı ikili işleçler soldan sağa operands ilişkilendirmek.

|İşleç|Açıklama|
|--------------|-----------------|
|**DEFINED** *(makroname)* **)**|*Makronamenin*geçerli tanım durumu için mantıksal bir değer üretir.|
|**EXIST (yol** *path* **)**|*Yolda*bir dosyanın varlığı için mantıksal bir değer üretir.|
|||
|**!**|Unary mantıksal NOT.|
|**~**|Unary bir tamamlayıcısı.|
|**-**|Unary olumsuzlama.|
|||
|**&#42;**|Çarpma.|
|**/**|Bölümü.|
|**%**|Modül (kalan).|
|||
|**+**|Ek.|
|**-**|Çıkarma.|
|||
|**\<\<**|Bitwise vardiya sola.|
|**>>**|Bitwise sağa kay.|
|||
|**\<=**|Daha az veya eşit.|
|**>=**|Daha büyük veya eşit.|
|**\<**|Daha az.|
|**>**|Daha büyük.|
|||
|**==**|Eşitlik.|
|**!=**|Eşitsiz -lik.|
|||
|**&**|Bitwise VE.|
|**^**|Bitwise XOR.|
|**&#124;**|Bitwise VEYA.|
|||
|**&&**|Mantıksal VE.|
|||
|**&#124;&#124;**|Mantıksal OR.|

> [!NOTE]
> Bitwise XOR işleci (**^**) kaçış karakteri yle aynıdır ve **^^** bir ifadede kullanıldığında (a)'dan kaçması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme Görevleri Dosyası Önişlemlerindeki İfadeler](expressions-in-makefile-preprocessing.md)

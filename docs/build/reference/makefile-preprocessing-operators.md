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
ms.openlocfilehash: 4101c2fe30bcba44e9b69ed4d6d022845e6e8904
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321585"
---
# <a name="makefile-preprocessing-operators"></a>Derleme Görevleri Dosyası Önişleme İşleçleri

Derleme görevleri dosyası önişleme ifadeler sabit değerler, çıkış kodlarından komutları, dizeler, makroları ve dosya sistemi yolları gibi davranan işleçleri kullanabilirsiniz. İfadeyi değerlendirmek için önişlemci ilk makroları genişletir ve ardından komutları yürütür ve ardından işlemleri gerçekleştirir. İşlem açık gruplandırma parantez içinde sırasına göre ve İşleç önceliği sırasına göre değerlendirilir. Sonuç sabit bir değerdir.

**TANIMLANAN** işleci, bir makro adı işlevi gören bir mantıksal işleç. İfade **TANIMLANAN (**_makroadı_**)** true ise *makroadı* tanımlanır, bile atanan bir değer yok. **TANIMLANAN** birlikte **! Eğer** veya **! ELSE IF** eşdeğerdir **! IFDEF** veya **! BAŞKA IFDEF**. Ancak, bu yönergeler aksine **TANIMLANAN** karmaşık ifadelerde kullanılabilir.

**Mevcut** işleci, bir dosya sistemi yolu işlevi gören bir mantıksal işleç. **Mevcut (**_yolu_**)** true ise *yolu* bulunmaktadır. Sonuç **mevcut** ikili ifadelerde kullanılabilir. Varsa *yolu* boşluklar içeriyorsa çift tırnak işaretleri içine alın.

İki dizeleri karşılaştırmak için eşitlik kullanın (**==**) işleci ve eşitsizlik (**! =**) işleci. Dize, çift tırnak içine alın.

Tamsayı sabitleri, birli işleçler için sayısal olumsuzlama kullanabilirsiniz (**-**), bir kullanıcının tamamlar (**~**) ve mantıksal olumsuzlama (**!**).

İfadeleri, aşağıdaki işleçleri kullanabilirsiniz. Eşit önceliğe sahip işleçler birlikte gruplanır ve öncelik sırasına göre azalan düzende gruplar listelenir. Birli işleçler, sağ işlenen ile ilişkilendirin. İkili işleçler eşit önceliğe sahip işlenenlerini soldan sağa ilişkilendirilir.

|İşleç|Açıklama|
|--------------|-----------------|
|**TANIMLANAN (** *makroadı* **)**|Geçerli tanım durumu için mantıksal bir değer üreten *makroadı*.|
|**Mevcut (** *yolu* **)**|Bir dosyaya varlığı için mantıksal bir değer üreten *yolu*.|
|||
|**\!**|Birli mantıksal değil.|
|**~**|Birli birinin tamamlayıcısı.|
|**-**|Tekli olumsuzlama.|
|||
|**&#42;**|Çarpma.|
|**/**|Bölme.|
|**%**|Modunu (kalanını).|
|||
|**+**|Ayrıca.|
|**-**|Çıkarma.|
|||
|**\<\<**|Sola bit tabanlı kaydırma.|
|**>>**|Bit düzeyinde kaydırma doğru.|
|||
|**\<=**|Küçüktür veya eşittir.|
|**>=**|Büyüktür veya eşittir.|
|**\<**|Küçüktür.|
|**>**|Büyüktür.|
|||
|**==**|Eşitlik.|
|**\!=**|Eşitsizlik.|
|||
|**&**|Bit düzeyinde and|
|**^**|Bit düzeyinde XOR.|
|**&#124;**|Bit düzeyinde OR.|
|||
|**&&**|Mantıksal and|
|||
|**&#124;&#124;**|Mantıksal OR.|

> [!NOTE]
> Bit düzeyinde XOR işleci (**^**) kaçış karakteri ile aynıdır ve kaçış karakterleri eklenmelidir (olarak **^^**) bir ifadede kullanıldığında.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme Görevleri Dosyası Ön İşlemlerindeki İfadeler](expressions-in-makefile-preprocessing.md)
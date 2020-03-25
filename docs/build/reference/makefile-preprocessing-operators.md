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
ms.openlocfilehash: 2276f6a3c28c6f2fac509ef0e4bc14cce9932582
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170469"
---
# <a name="makefile-preprocessing-operators"></a>Derleme Görevleri Dosyası Önişleme İşleçleri

Derleme görevleri dosyası ön işleme ifadeleri sabit değerler, komut, dizeler, makrolar ve dosya sistemi yollarından çıkış kodları üzerinde işlem yapan işleçleri kullanabilir. İfadeyi değerlendirmek için, önişlemci önce makroları genişletir, sonra komutları yürütür ve sonra işlemleri gerçekleştirir. İşlemler, parantez içinde açık gruplandırma sırasıyla ve sonra işleç önceliği sırasına göre değerlendirilir. Sonuç sabit bir değerdir.

**Tanımlı** işleç, makro adı üzerinde davranan mantıksal bir işleçtir. Atanan bir değere sahip olmasa bile, *makroadı* tanımlanmışsa **(** _makroadı_ **)** ifade true olur. Birlikte **tanımlanır** **!** Veya varsa **! AKSI TAKDIRDE** , öğesine eşdeğerdir **! IDEF** veya **! ELSE IFDEF**. Ancak, bu yönergelerin aksine, **tanımlanan** karmaşık ifadelerde bu şekilde kullanılabilir.

**EXIST** işleci, bir dosya sistemi yolu üzerinde davranan mantıksal bir işleçtir. *Yol* varsa, **mevcut (** _Path_ **)** değeri true 'dur. **Var** olan sonucu ikili ifadelerde kullanılabilir. *Yol* boşluk içeriyorsa, çift tırnak işaretleri içine alın.

İki dizeyi karşılaştırmak için eşitlik ( **==** ) işlecini veya eşitsizlik ( **! =** ) işlecini kullanın. Dizeleri çift tırnak işaretleri içine alın.

Tamsayı sabitleri birli işleçleri ( **-** ), bir tane tamamlama ( **~** ) ve mantıksal değilleme ( **!** ) için kullanabilir.

İfadeler aşağıdaki işleçleri kullanabilir. Eşit önceliğe sahip işleçler birlikte gruplandırılır ve gruplar azalan öncelik sırasıyla listelenir. Birli İşleçler, işleneni sağ ile ilişkilendirir. Eşit önceliğe sahip ikili işleçler, işlenenleri soldan sağa ilişkilendirir.

|İşleç|Açıklama|
|--------------|-----------------|
|**Tanımlı (** *makroadı* **)**|*Makroadı*öğesinin geçerli tanım durumu için bir mantıksal değer üretir.|
|**Var (** *yol* **)**|*Yoldaki*bir dosyanın varlığı için bir mantıksal değer üretir.|
|||
|**!**|Birli mantıksal DEĞIL.|
|**~**|Birli bir tamamlayıcı.|
|**-**|Birli olumsuzlama.|
|||
|**&#42;**|Çarpma.|
|**/**|Bölme.|
|**%**|Mod (geri kalan).|
|||
|**+**|Ayrıca.|
|**-**|Çıkarma.|
|||
|**\<\<**|Bit düzeyinde kaydırma sola.|
|**>>**|Bit düzeyinde kaydırma hakkı.|
|||
|**\<=**|Küçüktür veya eşittir.|
|**>=**|Büyük veya eşittir.|
|**\<**|Küçüktür.|
|**>**|Büyüktür.|
|||
|**==**|Eþit.|
|**!=**|Olmama.|
|||
|**&**|Bit düzeyinde and|
|**^**|Bit düzeyinde XOR.|
|**&#124;**|Bit düzeyinde OR.|
|||
|**&&**|Mantıksal AND.|
|||
|**&#124;&#124;**|Mantıksal OR.|

> [!NOTE]
> Bit düzeyinde XOR işleci ( **^** ) kaçış karakteriyle aynıdır ve bir ifadede kullanıldığı zaman kaçışın ( **^^** olarak) olması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme Görevleri Dosyası Ön İşlemlerindeki İfadeler](expressions-in-makefile-preprocessing.md)

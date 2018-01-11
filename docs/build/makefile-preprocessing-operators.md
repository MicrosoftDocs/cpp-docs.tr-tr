---
title: "Derleme görevleri dosyası ön işleme işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59007bdabc81b5fe49aa4b5265dc0fc73ef4f0b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-operators"></a>Derleme Görevleri Dosyası Önişleme İşleçleri
Derleme görevleri dosyası önişleme ifadeleri hareket işleçleri sabit değerleri, çıkış kodlarından komutları, dizeleri, makroları ve dosya sistemi yolları kullanabilirsiniz. İfade değerlendirmek için Önişlemci makroları, ilk genişletir ve komutları yürütür ve işlemleri gerçekleştirir. Operations parantez içinde açık gruplandırma sırasına göre ve İşleç önceliği sırasına göre değerlendirilir. Sonuç sabit bir değerdir.  
  
 `DEFINED` İşlecidir makrosu adına görevi gören bir mantıksal işleç. İfade `DEFINED(` *makroadı* `)` true ise *makroadı* atanmış bir değere sahip değil olsa bile, tanımlıdır. `DEFINED`ile birlikte `!IF` veya `!ELSE IF` eşdeğerdir `!IFDEF` veya `!ELSE IFDEF`. Ancak, bu yönergeleri aksine `DEFINED` karmaşık ifadeler kullanılabilir.  
  
 `EXIST` İşlecidir bir dosya sistemi yolu görevi gören bir mantıksal işleç. `EXIST(`*yol* `)` true ise *yolu* bulunmaktadır. Sonuç `EXIST` ikili ifadeler kullanılabilir. Varsa *yolu* alanları içerir çift tırnak işaretleri içine alın.  
  
 İki dizeleri karşılaştırmak için eşitlik kullanın (`==`) işleci veya eşitsizlik (`!=`) işleci. Dizeleri çift tırnak işaretleri içine alın.  
  
 Tamsayı sabitleri için sayısal değilleme birli işleçleri kullanabilirsiniz (`-`), bir kullanıcının tamamlayan (`~`) ve mantıksal olumsuzlaştırma (`!`).  
  
 İfadeler aşağıdaki işleçleri kullanabilirsiniz. Eşit öncelik işleçleri birlikte gruplanır ve öncelik sırasına göre azalan düzende gruplar listelenir. Birli işleçleri sağ işleneni ile ilişkilendirin. İkili işleçler eşit öncelik işlenenler soldan sağa ilişkilendirin.  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|`DEFINED(`*makroadı*`)`|Geçerli tanımı durumu için mantıksal bir değer üreten *makroadı*.|  
|`EXIST(`*yolu*`)`|Mantıksal bir değer, bir dosyaya varlığı oluşturur *yolu*.|  
|||  
|`!`|Birli mantıksal değil.|  
|`~`|Birli birinin tamamlama.|  
|`-`|Tekli değilleme.|  
|||  
|`*`|Çarpma.|  
|`/`|Bölme.|  
|`%`|Mod (Kalan).|  
|||  
|`+`|Ayrıca.|  
|`-`|Çıkarma.|  
|||  
|`<<`|Sola bit tabanlı kaydırma.|  
|`>>`|Bit kaydırma doğru.|  
|||  
|`<=`|Küçüktür veya eşittir.|  
|`>=`|Büyüktür veya eşittir.|  
|`<`|Küçüktür.|  
|`>`|Büyüktür.|  
|||  
|`==`|Eşitlik.|  
|`!=`|Eşitsizlik.|  
|||  
|`&`|Bit düzeyinde and|  
|`^`|Bit düzeyinde XOR.|  
|`&#124;`|Bit düzeyinde OR.|  
|||  
|`&&`|Mantıksal and|  
|||  
|`&#124;&#124;`|Mantıksal OR.|  
  
> [!NOTE]
>  Bit düzeyinde XOR işleci (`^`) kaçış karakteri ile aynıdır ve kaçış uygulanmalıdır (olarak `^^`) bir ifadede kullanıldığında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Ön İşlemlerindeki İfadeler](../build/expressions-in-makefile-preprocessing.md)
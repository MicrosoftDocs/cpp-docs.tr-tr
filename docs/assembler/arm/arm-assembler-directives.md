---
title: ARM Assembler yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5ab97fb9ccdff19206b829383c622efd3f7921
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="arm-assembler-directives"></a>ARM Assembler Yönergeleri
Çoğunlukla, Microsoft ARM assembler Bölüm 7'de belgelenen ARM assembler dili kullanan [ARM assembler araçları Kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=246102). Ancak, bazı derleme yönergesi Microsoft uygulamaları ARM derleme yönergeleri farklı. Bu makalede farklar açıklanmaktadır.  
  
## <a name="microsoft-implementations-of-arm-assembly-directives"></a>Microsoft uygulamaları ARM derleme yönergesi  
 ALAN  
 Bu alan öznitelikleri Microsoft ARM assembler destekler: ALIGN, kod, CODEALIGN, verileri, NOINIT, salt okunur, READWRITE, Flash, ARM.  
  
 Kaydırma kutusu ve ARM dışında tüm açıklandığı gibi iş [ARM assembler araçları Kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=246102).  
  
 Microsoft ARM assembler Flash kod bölümünde Flash kodunu içerir ve kod bölümler için varsayılan değer gösterir.  ARM bölüm ARM kod içerdiğini gösterir.  
  
 ATTR  
 Desteklenmez.  
  
 KODU16  
 Microsoft ARM assembler izin verme öncesi UAL Flash sözdizimi gösterdiğinden desteklenmiyor.  Flash yönergesi, bunun yerine, UAL sözdizimi ile birlikte kullanın.  
  
 ORTAK  
 Ortak bölge için bir hizalama belirtimi desteklenmiyor.  
  
 DCDO  
 Desteklenmez.  
  
 DN, QN, SN  
 Bir tür veya bir kayıt diğer yolundaki belirtimi desteklenmiyor.  
  
 GİRİŞ  
 Desteklenmez.  
  
 EQU  
 Bir tür için tanımlanmış simgenin belirtimi desteklenmiyor.  
  
 Dışarı aktarma ve genel  
 ```  
EXPORTsym {[type]}  
```  
  
 `sym` dışa aktarılacak simgenin olur.  `[type]`, belirtilmişse, ya da olabilir `[DATA]` simgenin veri noktalarını göstermek için veya `[FUNC]` simgenin için kod noktaları belirtmek için.  
  
 Bir eş anlamlı dışa aktarma için geneldir.  
  
 EXPORTAS  
 Desteklenmez.  
  
 ÇERÇEVE  
 Desteklenmez.  
  
 İŞLEV ve PROC  
 Özel bir belirtimi derleme sözdizimini destekler; ancak çağıran Kaydet ve Aranan tasarrufu olanlar yazmaçlar listeleyerek yordamlarını çağırma Microsoft ARM assembler söz dizimini kabul eder ancak kayıt listelerini göz ardı eder.  Derleyici tarafından üretilen hata ayıklama bilgileri yalnızca çağırma varsayılan destekler.  
  
 İçeri aktarma ve EXTERN  
 ```  
IMPORT sym{, WEAK alias{, TYPE t}}  
```  
  
 `sym` İçeri aktarılacak simgenin adıdır.  
  
 ZAYIF varsa `alias` belirtilirse, bu gösterir `sym` zayıf bir dış. Hiçbir tanımlarında bağlantı aynı anda bulunur sonra bağlamak yerine tüm başvuruları `alias`.  
  
 Varsa türü `t` belirtilmemişse `t` nasıl bağlayıcı çözümlemeye gösteren `sym`.  Bu değerleri için `t` mümkündür:   
1 — kitaplığı araması gerçekleştirme `sym`  
2 — kitaplığı aramasını gerçekleştirin `sym`  
3 —`sym` için diğer ad olduğu `alias` (varsayılan)  
  
 EXTERN olduğu alma eşanlamlısı hariç `sym` yalnızca başvuru geçerli derlemesindeki varsa alınır.  
  
 MACRO  
 Makro koşulu kodunu tutmak için bir değişken kullanımı desteklenmiyor. Varsayılan değerleri makrosu parametreleri desteklenmez.  
  
 NOFP  
 Desteklenmez.  
  
 OPT, TTL, SUBT  
 Microsoft ARM assembler listelerini oluşturmadığı desteklenmiyor.  
  
 PRESERVE8  
 Desteklenmez.  
  
 RELOC  
 `RELOC n` yalnızca bir yönerge veya bir veri tanım yönergesi izleyebilirsiniz. "Yerleştirildiğinde anonim hiçbir sembolü" dir.  
  
 GEREKTİRİR  
 Desteklenmez.  
  
 REQUIRE8  
 Desteklenmez.  
  
 THUMBX  
 Microsoft ARM assembler Flash 2EE yönerge kümesi desteklemediği için desteklenmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ARM Assembler komut satırı başvurusu](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Tanılama İletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)
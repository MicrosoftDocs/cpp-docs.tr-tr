---
title: "Derleme görevleri dosyası ön işleme yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs: C++
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bc73a86b0772b13731aaf7ac4e2ef0760caa8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-directives"></a>Derleme Görevleri Dosyası Önişleme Yönergeleri
Önişleme yönergeleri büyük küçük harfe duyarlı değildir. İlk ünlem işareti (!), satır başında yer almalıdır. Sıfır veya daha fazla boşluk veya sekmeler girinti ünlem sonra ortaya çıkabilir.  
  
 **! CMDSWITCHES**  
 {**+**&#124;  **-** }*seçeneği*... Her kapatır *seçeneği* açmak veya kapatmak listelenir. Boşluk veya sekmeler önce görünmelidir + veya - işleci; Hiçbiri arasında işleci görüntülenebilir ve [seçeneği harf](../build/nmake-options.md). Harfler, büyük/küçük harfe duyarlı değildir ve bir eğik çizgi (/) belirtilir. Bazı seçenekleri ve diğerleri devre dışı bırakmak için ayrı belirtimlerini kullanmak **! CMDSWITCHES**.  
  
 Yalnızca /D / t, /N ve /S derleme görevleri dosyası içinde kullanılabilir. Tools.ini tüm seçenekleri izin dışında /F, / Help, / nologo, /, X ve /?. Açıklama bloğunda belirtilen değişiklikleri sonraki açıklama bloğu kadar etkili olmaz. Bu yönerge güncelleştirmeleri **MAKEFLAGS**; varsa değişiklikleri sırasında özyineleme devralındığı **MAKEFLAGS** belirtilir.  
  
 **! HATA***metin*   
 Görüntüler *metin* hatası U1050 sonra durur NMAKE, olsa bile, / k, / t, **. Yoksay**, **! CMDSWITCHES**, veya tire (-) komutu değiştiricisi kullanılır. Boşluk veya önce sekmeler *metin* göz ardı edilir.  
  
 **! İleti***metin*   
 Görüntüler *metin* için standart çıktı. Boşluk veya önce sekmeler *metin* göz ardı edilir.  
  
 **! DAHİL**[  **\<** ] *filename*[  **>** ]  
 Okur *filename* derleme görevleri dosyası, ardından geçerli derleme görevleri dosyası ile devam eder. NMAKE arar *filename* ilk belirtilen ya da geçerli dizinde sonra dizinleri herhangi aracılığıyla yinelemeli olarak üst derleme görevleri dosyaları, daha sonra *filename* açılı ayraç içine (\<>), tarafından belirtilen dizinde **INCLUDE** başlangıçta INCLUDE ortam değişkeni ayarlanır makrosu. Geçirmek kullanışlı **. SONEKLERİ** ayarları **. DEĞERLİ**ve yinelemeli derleme görevleri dosyaları çıkarım kuralları.  
  
 **! EĞER**  `constantexpression`  
 İşler arasındaki deyimleri **! Eğer** ve sonraki **! ELSE** veya `!ENDIF` varsa `constantexpression` sıfır olmayan bir değere değerlendirir.  
  
 **! IFDEF***makroadı*   
 İşler arasındaki deyimleri `!IFDEF` ve sonraki **! ELSE** veya `!ENDIF` varsa *makroadı* tanımlanır. Null makro tanımlanacak olarak kabul edilir.  
  
 **! IFNDEF***makroadı*   
 İşler arasındaki deyimleri **! IFNDEF** ve sonraki **! ELSE** veya `!ENDIF` varsa *makroadı* tanımlı değil.  
  
 **! ELSE**[**IF** *sabitDeyim'in* &#124; **IFDEF** *makroadı*&#124; **IFNDEF** *makroadı*]  
 İşler arasındaki deyimleri **! ELSE** ve sonraki `!ENDIF` , önceki **! Eğer**, `!IFDEF`, veya **! IFNDEF** sıfır olarak değerlendirilen ifade. İsteğe bağlı anahtar sözcükleri daha fazla ön işleme Denetim verin.  
  
 **! ELSEIF**  
 Eş **! ELSE IF**.  
  
 **! ELSEIFDEF**  
 Eş **! ELSE IFDEF**.  
  
 **! ELSEIFNDEF**  
 Eş **! ELSE IFNDEF**.  
  
 `!ENDIF`  
 Sonunu işaretler bir **! Eğer**, `!IFDEF`, veya **! IFNDEF** bloğu. Sonra herhangi bir metin `!ENDIF` aynı satırda göz ardı edilir.  
  
 **! UNDEF***makroadı*   
 Undefines *makroadı*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Ön İşlemi](../build/makefile-preprocessing.md)
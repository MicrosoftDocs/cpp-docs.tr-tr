---
title: Derleme Görevleri Dosyası Önişleme Yönergeleri
ms.date: 06/14/2018
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
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
ms.openlocfilehash: 0945d0e1c149b7e1ab31b0dbbd5003f8b15a1e4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321572"
---
# <a name="makefile-preprocessing-directives"></a>Derleme Görevleri Dosyası Önişleme Yönergeleri

Ön işleme yönergeleri büyük/küçük harfe duyarlı değildir. İlk ünlem işareti (!), satır başında yer almalıdır. Sıfır veya daha fazla boşluk veya sekme girinti ünlem sonra görünebilir.

- **! CMDSWITCHES** {**+** &#124; **-**}*seçeneği* ...

   Her kapatır *seçeneği* açıp listelenir. Boşluk veya sekme önce görünmelidir + veya - işleç; Hiçbiri arasında işleci görünebilir ve [seçeneği harf](nmake-options.md). Harf, büyük/küçük harfe duyarlı değildir ve bir eğik çizgi (/) belirtildi. Bazı seçenekleri ve diğer devre dışı bırakmak için ayrı belirtimlerini kullanın **! CMDSWITCHES**.

   Yalnızca /D / ı /N ve /S bir derleme görevleri dosyasında kullanılabilir. Tools.ini tüm seçenekleri izin dışında /F, / Help, / nologo, /, X ve /? Bir açıklama bloğu içinde belirtilen değişiklikler sonraki açıklama bloğu kadar etkili olmaz. Bu yönerge güncelleştirmeleri **MAKEFLAGS**; değişiklikleri, özyineleme sırasında devralınan **MAKEFLAGS** belirtilir.

- **! HATA** *metin*

   Görüntüler *metin* hatası U1050 sonra durur NMAKE, olsa bile, /K, / ı, **. Yoksay**, **! CMDSWITCHES**, veya tire (-) komut değiştiricisi kullanılır. Boşluk veya sekme önce *metin* göz ardı edilir.

- **! İleti** *metin*

   Görüntüler *metin* standart çıktıya. Boşluk veya sekme önce *metin* göz ardı edilir.

- **! DAHİL** [ **\<** ] *filename* [ **>** ]

   Okur *filename* derleme görevleri dosyası, ardından geçerli derleme görevleri dosyası ile devam eder. NMAKE arar *filename* ilk belirtilen ya da geçerli dizinde ardından dizinlerinde aracılığıyla yinelemeli olarak ana derleme görevleri dosyalarını, daha sonra *filename* açılı ayraç içine alınır (\<>), tarafından belirtilen dizinlerde **INCLUDE** makrosu, başlangıçta için Include ortam değişkeni ayarlanır. Geçirmek kullanışlı **. SONEKLERİ** ayarları **. DEĞERLİ**ve yinelemeli derleme görevleri dosyaları için çıkarım kuralları.

- **! Eğer** *constant_expression*

   İşler arasındaki **! Eğer** ve sonraki **! BAŞKA** veya **! ENDIF** varsa *constant_expression* sıfır dışında bir değeri değerlendirir.

- **! IFDEF** *makroadı*

   İşler arasındaki **! IFDEF** ve sonraki **! BAŞKA** veya **! ENDIF** varsa *makroadı* tanımlanır. Null makro tanımlanmış kabul edilir.

- **! IFNDEF** *makroadı*

   İşler arasındaki **! IFNDEF** ve sonraki **! BAŞKA** veya **! ENDIF** varsa *makroadı* tanımlı değil.

- **!ELSE** [**IF** *constant_expression* &#124; **IFDEF** *macroname* &#124; **IFNDEF** *macroname*]

   İşler arasındaki **! BAŞKA** ve sonraki **! ENDIF** , önceden **! Eğer**, **! IFDEF**, veya **! IFNDEF** sıfır olarak değerlendirilen bir ifade. İsteğe bağlı anahtar sözcük, daha fazla ön işleme, Denetim verir.

- **! ELSEIF**

   Eşanlamlısı **! ELSE IF**.

- **! ELSEIFDEF**

   Eşanlamlısı **! BAŞKA IFDEF**.

- **! ELSEIFNDEF**

   Eşanlamlısı **! BAŞKA IFNDEF**.

- **! ENDIF**

   Sonunu işaretleyen bir **! Eğer**, **! IFDEF**, veya **! IFNDEF** blok. Sonra herhangi bir metin **! ENDIF** aynı satırdaki göz ardı edilir.

- **! UNDEF** *makroadı*

   Tanımsızı *makroadı*.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme Görevleri Dosyası Ön İşlemi](makefile-preprocessing.md)
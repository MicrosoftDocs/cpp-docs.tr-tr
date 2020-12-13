---
description: 'Daha fazla bilgi için: makefile ön Işleme yönergeleri'
title: Derleme Görevleri Dosyası Önişleme Yönergeleri
ms.date: 08/11/2019
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
ms.openlocfilehash: 7c394e3547044be661fea5a8ec86f05a3b93e967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138079"
---
# <a name="makefile-preprocessing-directives"></a>Derleme Görevleri Dosyası Önişleme Yönergeleri

Ön işleme yönergeleri büyük/küçük harfe duyarlı değildir. İlk ünlem işareti (!) satırın başlangıcında görünmelidir. Girintileme için, ünlem işaretiyle sıfır veya daha fazla boşluk veya sekme görünebilir.

- `!CMDSWITCHES` { `+` &#124; `-` }*seçeneği* ...

   Üzerinde listelenen her *seçeneği* kapatır veya kapatır. Boşluk veya sekmeler `+` veya işleçten önce gelmelidir `-` ; işleç ve [seçenek harfleri](running-nmake.md#nmake-options)arasında hiçbiri görünmeyebilir. Harfler büyük küçük harfe duyarlı değildir ve eğik çizgi () olmadan belirtilir `/` . Bazı seçenekleri açıp diğerlerini devre dışı bırakmak için, ayrı belirtimlerini kullanın `!CMDSWITCHES` .

   Derleme görevleri dosyası içinde yalnızca/D,/I,/N ve/S kullanılabilir. Tools.ini,/F,/HELP,/NOLOGO,/X ve/? dışında tüm seçeneklere izin verilir. Açıklama bloğunda belirtilen değişiklikler bir sonraki açıklama bloğuna kadar etkili olmaz. Bu yönerge **makeflags**'i güncelleştirir; **makeflags** belirtilmişse, değişiklikler özyineleme sırasında devralınır.

- `!ERROR`*metin*

   /K  ,/ı, `.IGNORE` , `!CMDSWITCHES` , veya Dash ( `-` ) komut değiştiricisi kullanılıyorsa, U1050 Error, ardından durursa NMAKE şeklinde metin görüntüler. *Metinden* önce boşluklar veya sekmeler yok sayılır.

- `!MESSAGE`*metin*

   Standart çıktıya *metin* görüntüler. *Metinden* önce boşluklar veya sekmeler yok sayılır.

- `!INCLUDE` [ `<` ] *filename* [ `>` ]

   *Dosya adını* derleme görevleri dosyası olarak okur, ardından geçerli derleme görevleri dosyası ile devam eder. NMAKE, belirtilen veya geçerli dizinde önce *dosya adını* arar, sonra herhangi bir üst makefiles dizininde özyinelemeli olarak, *dosya adı* açılı ayraç () ile çevrelenmiş ve `< >` Bu, ilk olarak INCLUDE ortam değişkenine ayarlanmış olan **içerme** makrosu tarafından belirtilen dizinlerde. `.SUFFIXES` `.PRECIOUS` Özyinelemeli makefiles 'a ayarları, ve çıkarım kurallarını geçirmek için kullanışlıdır.

- `!IF`*constant_expression*

   `!IF`İle Next `!ELSE` veya `!ENDIF` IF *constant_expression* deyimleri sıfır dışında bir değere değerlendirir.

- `!IFDEF`*makroadı*

   `!IFDEF`Ve sonraki ya da makroadı arasında işlem deyimleri `!ELSE` `!ENDIF` tanımlanmıştır.  Null bir makronun tanımlanması kabul edilir.

- `!IFNDEF`*makroadı*

   `!IFNDEF`Ve sonraki ya da makroadı arasında işlem deyimleri `!ELSE` `!ENDIF` tanımlı değildir. 

- `!ELSE` [ `IF` *constant_expression* &#124; `IFDEF` *makroadı* &#124; `IFNDEF` *makroadı*]

   `!ELSE` `!ENDIF` `!IF` `!IFDEF` Using,, veya `!IFNDEF` deyimi sıfır olarak değerlendiriliyorsa, ve ileri arasındaki deyimleri işler. İsteğe bağlı anahtar sözcükler, ön işleme için daha fazla denetim sağlar.

- `!ELSEIF`

   İçin eş anlamlı `!ELSE IF`.

- `!ELSEIFDEF`

   İçin eş anlamlı `!ELSE IFDEF`.

- `!ELSEIFNDEF`

   İçin eş anlamlı `!ELSE IFNDEF`.

- `!ENDIF`

   `!IF`, `!IFDEF` Veya bloğunun sonunu işaretler `!IFNDEF` . Aynı satırdan sonra herhangi bir metin `!ENDIF` yok sayılır.

- `!UNDEF`*makroadı*

   *Makroadı* öğesini kaldır.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme görevleri dosyası ön Işleme](makefile-preprocessing.md)

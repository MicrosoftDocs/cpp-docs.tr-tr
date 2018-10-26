---
title: Kod sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], code pages
- ANSI [C++], code pages
- system-default code page
- multibyte code pages [C++]
- localization [C++], code pages
- code pages [C++], types of
- locale code pages [C++]
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eafdf3a140dd8a5976cf2fe8554b3b076111b74
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060513"
---
# <a name="code-pages"></a>Kod Sayfaları

A *kod sayfası* sayılar, noktalama işaretleri ve diğer karakterleri dahil edebilirsiniz bir karakter kümesi. Farklı dillerde ve yerel ayarlar, farklı kod sayfalarını kullanabilir. Örneğin, ANSI kod sayfası 1252 İngilizce ve en Avrupa dilleri için kullanılır; OEM kod sayfası 932'de Japonca Kanji için kullanılır.

Bir kod sayfası bir tablodaki tek baytlık değer veya değerlerini çok baytlı karakter eşlemesi olarak gösterilebilir. Birçok kod sayfaları ASCII karakter aralığı 0x00 - 0x7F karakter kümesini paylaşır.

Microsoft çalışma zamanı kitaplığı aşağıdaki kod sayfaları türlerini kullanır:

- Sistem varsayılan ANSI kod sayfası. Varsayılan olarak, başlatma sırasında çalışma zamanı otomatik olarak çok baytlı kod sayfası işletim sisteminden alınan sistem varsayılan ANSI kod sayfasına ayarlar. Çağrı:

    ```C
    setlocale ( LC_ALL, "" );
    ```

   Ayrıca yerel sistem varsayılan ANSI kod sayfasına ayarlar.

- Yerel ayar kod sayfası. Çalışma zamanı yordamları bir dizi davranışını yerel ayar kod sayfası içeren geçerli yerel ayarda bağlıdır. (Daha fazla bilgi için [yerel ayara bağımlı yordamlar](../c-runtime-library/locale.md).) Varsayılan olarak, Microsoft Çalışma Zamanı Kitaplığı'ndaki tüm yerel ayara bağımlı yordamlar için "C" yerel karşılık gelen kod sayfasını kullanın. Çalışma zamanında değiştirebilir veya yerel ayar kod sayfasına çağrısı ile sorgu [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).

- Çok baytlı kod sayfası. Çalışma Zamanı Kitaplığı'nda çok baytlı karakter yordamlarını çoğunu davranışını geçerli çok baytlı kod sayfası ayarını bağlıdır. Varsayılan olarak, bu yordamların sistem varsayılan ANSI kod sayfasını kullanın. Çalışma zamanında sorgulamak ve çok baytlı kod sayfası ile Değiştir [_getmbcp](../c-runtime-library/reference/getmbcp.md) ve [_setmbcp](../c-runtime-library/reference/setmbcp.md)sırasıyla.

- "C" yerel ANSI C programları geleneksel yürüttünüz yerel ayarına karşılık gelecek şekilde tanımlanır. "C" yerel ("C" kod sayfası) için kod sayfası, ASCII karakter kümesi karşılık gelir. Örneğin, "C" yerel olarak **islower** değerlerini 0x61 - yalnızca 0x7A true değerini döndürür. Başka bir yerel ayarında, **islower** bu yerel ayar tarafından tanımlandığı şekilde bu yanı sıra diğer değerleri true döndürebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
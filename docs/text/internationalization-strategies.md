---
title: Uluslararası Duruma Getirme Stratejileri
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
ms.openlocfilehash: 91f4805152944202b7d3f7f45fce494f7e9d81af
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53626688"
---
# <a name="internationalization-strategies"></a>Uluslararası Duruma Getirme Stratejileri

Hedef işletim sistemleri ve pazarlara bağlı olarak birkaç uluslararası duruma getirme stratejileri vardır:

- Uygulamanız, Unicode kullanır.

   Unicode özgü işlevini kullanın ve (ANSI karakterlerini programınızın bazı bölümlerinde özel amaçlar için kullanabilirsiniz, ancak) tüm karakterlerin 16 bit genişliğinde olan. C çalışma zamanı kitaplığı işlevleri, makroları ve veri türleri için salt Unicode programlama sağlar. MFC tam Unicode etkindir.

- Uygulamanız MBCS kullanır ve Win32 herhangi bir platform üzerinde çalıştırılabilir.

   MBCS özgü işlevleri kullanırsınız. Dizeleri tek baytlık karakteri, çift baytlık karakterler veya her ikisi de içerebilir. C çalışma zamanı kitaplığı işlevleri, makroları ve veri türleri için yalnızca MBCS programlama sağlar. MFC tam MBCS etkindir.

- Uygulamanız için kaynak kodu tam taşınabilirlik için yazılan — simgesiyle yeniden derlemeden tarafından `_UNICODE` veya sembol `_MBCS` tanımlanan, hangisini sürümlerini oluşturabilir. Daha fazla bilgi için [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

   Tam olarak taşınabilir C çalışma zamanı işlevleri, makroları ve veri türleri kullanırsınız. MFC'nin esneklik herhangi birini bu stratejiler destekler.

Bu konu başlıkları geri kalanında Unicode veya MBCS olarak oluşturabileceğiniz tamamen taşınabilir kod yazmaya odaklanmasına.

## <a name="see-also"></a>Ayrıca Bkz.

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
[Yerel Ayarlar ve Kod Sayfaları](../text/locales-and-code-pages.md)

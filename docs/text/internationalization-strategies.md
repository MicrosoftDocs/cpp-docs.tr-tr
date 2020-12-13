---
description: 'Daha fazla bilgi edinin: Uluslararası duruma getirme stratejileri'
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
ms.openlocfilehash: 51570a3e340a8af0a9f16f8212aa11f6bf3119b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331182"
---
# <a name="internationalization-strategies"></a>Uluslararası Duruma Getirme Stratejileri

Hedef işletim sistemlerine ve pazarlarına bağlı olarak, çeşitli uluslararası duruma getirme stratejileriniz vardır:

- Uygulamanız Unicode kullanır.

   Unicode 'a özgü işlevselliği kullanın ve tüm karakterler 16 bit geniştir (ancak özel amaçlar için programınızın bazı bölümlerinde ANSI karakterleri de kullanabilirsiniz). C çalışma zamanı kitaplığı, salt Unicode programlama için işlevler, makrolar ve veri türleri sağlar. MFC tam Unicode özellikli.

- Uygulamanız MBCS kullanır ve herhangi bir Win32 platformunda çalıştırılabilir.

   MBCS 'ye özgü işlevleri kullanıyorsunuz. Dizeler tek baytlı karakterler, çift baytlık karakterler veya her ikisini içerebilir. C çalışma zamanı kitaplığı, yalnızca MBCS programlama için işlevler, makrolar ve veri türleri sağlar. MFC tamamen MBCS etkindir.

- Uygulamanızın kaynak kodu, tüm taşınabilirlik için yazılmıştır — sembol `_UNICODE` veya tanımlanmış sembol ile yeniden derleme yaparak `_MBCS` , birini kullanan sürümler üretebilirsiniz. Daha fazla bilgi için, bkz. [Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

   Tamamen taşınabilir C çalışma zamanı işlevlerini, makroları ve veri türlerini kullanırsınız. MFC 'nin esnekliği bu stratejilerin herhangi birini destekler.

Bu konuların geri kalanı, Unicode veya MBCS olarak oluşturabileceğiniz tamamen taşınabilir kod yazmaya odaklanmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[Unicode ve MBCS](../text/unicode-and-mbcs.md)<br/>
[Yerel ayarlar ve kod sayfaları](../text/locales-and-code-pages.md)

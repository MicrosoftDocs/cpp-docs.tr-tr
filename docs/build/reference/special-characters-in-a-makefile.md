---
description: 'Hakkında daha fazla bilgi için: derleme görevleri dosyasındaki özel karakterler'
title: Derleme Görevleri Dosyasındaki Özel Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: 22b8f6dd82191c88a23eaf1dabb551d468293a42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224679"
---
# <a name="special-characters-in-a-makefile"></a>Derleme Görevleri Dosyasındaki Özel Karakterler

Bir NMAKE özel karakterini sabit karakter olarak kullanmak için, önüne bir şapka işareti (^) koyun. NMAKE diğer karakterlerden önce gelen yüzleri yoksayar. Özel karakterler şunlardır:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Tırnak işaretli bir dize içindeki bir şapka (^), sabit bir giriş işareti karakteri olarak değerlendirilir. Satırın sonundaki bir giriş işareti, bir dizeye veya makroya sabit bir yeni satır karakteri ekler.

Makrolar içinde, bir yeni satır karakteri gelen ters eğik çizgi (), bir \\ boşluk ile değiştirilmiştir.

Komutlarda yüzde simgesi (%) bir dosya belirticisidir. Bir komutta% harfine göstermek için, bir çift yüzde işareti (%%) belirtin tek bir yerde. Diğer durumlarda NMAKE tek bir% harfi yorumlaması, ancak her zaman%% öğesini tek bir% olarak yorumlar. Bu nedenle,%% sabit değerini göstermek için,%%%, veya yüzde dört işareti (%%%%) belirtin.

Bir komutta bir sabit karakter olarak dolar işareti ($) kullanmak için iki dolar işareti ($ $) belirtin. Bu yöntem, ^ $ çalıştığı diğer durumlarda da kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyası içeriği](contents-of-a-makefile.md)

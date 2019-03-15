---
title: Derleme Görevleri Dosyasındaki Özel Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: d915b182d72b4251f416433642cd8b1832b80e08
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823491"
---
# <a name="special-characters-in-a-makefile"></a>Derleme Görevleri Dosyasındaki Özel Karakterler

NMAKE özel karakter değişmez değer olarak kullanmak için önündeki bir şapka (^) yerleştirin. NMAKE diğer karakterlerden önce düzeltme işaretleri yok sayar. Özel karakterler şunlardır:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Tırnak işaretli dize içindeki bir şapka (^) bir değişmez değer şapka karakteri kabul edilir. Bir giriş işaretini bir satır sonunda bir değişmez değer yeni satır karakteri bir dize veya makro ekler.

Makrolardaki ters eğik çizgi (\\) ve ardından tarafından bir yeni satır karakteri bir boşluk ile değiştirilir.

Komutlarda, yüzde işareti (%) bir dosya tanımlayıcısı var. % Gerçek anlamda bir komutu temsil etmek için bir çift yüzde işareti (%) belirtin. tek bir tane yerine. Tek bir % NMAKE diğer durumlarda, tam anlamıyla yorumlar, ancak her zaman bir çift yorumlar %% tek bir %. Bu nedenle, bir sabit değer temsil etmek için %%, ya da üç yüzde işaretleri belirtin %%%, veya dört yüzde işaretleri %%%.

Değişmez değer komutunda dolar işareti ($) kullanmak için iki dolar işareti ($$) belirtin. Bu yöntem, diğer durumlarda kullanılabilir olduğu ^ $ çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyası İçeriği](contents-of-a-makefile.md)

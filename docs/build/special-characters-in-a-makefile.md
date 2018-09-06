---
title: Derleme görevleri dosyasındaki özel karakterler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40d9ad442e4838ee837c93ada0352f230fc0cbed
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894440"
---
# <a name="special-characters-in-a-makefile"></a>Derleme Görevleri Dosyasındaki Özel Karakterler

NMAKE özel karakter değişmez değer olarak kullanmak için önündeki bir şapka (^) yerleştirin. NMAKE diğer karakterlerden önce düzeltme işaretleri yok sayar. Özel karakterler şunlardır:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`  

Tırnak işaretli dize içindeki bir şapka (^) bir değişmez değer şapka karakteri kabul edilir. Bir giriş işaretini bir satır sonunda bir değişmez değer yeni satır karakteri bir dize veya makro ekler.

Makrolardaki ters eğik çizgi (\\) ve ardından tarafından bir yeni satır karakteri bir boşluk ile değiştirilir.

Komutlarda, yüzde işareti (%) bir dosya tanımlayıcısı ' dir. % Gerçek anlamda bir komutu temsil etmek için bir çift yüzde işareti (%) yerine tek bir tane belirtin. Tek bir % NMAKE diğer durumlarda, tam anlamıyla yorumlar, ancak her zaman bir çift yorumlar %% tek bir %. Bu nedenle, bir sabit değer temsil etmek için %%, ya da üç yüzde işaretleri belirtin %%%, veya dört yüzde işaretleri %%%.

Değişmez değer komutunda dolar işareti ($) kullanmak için iki dolar işareti ($$) belirtin. Bu yöntem, diğer durumlarda kullanılabilir olduğu ^ $ çalışır.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyası İçeriği](../build/contents-of-a-makefile.md)
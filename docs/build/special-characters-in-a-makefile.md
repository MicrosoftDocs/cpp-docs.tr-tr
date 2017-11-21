---
title: "Derleme görevleri dosyasındaki özel karakterler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53b2457c87e587b4e1ef13e53bf2dfcdd4800d7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="special-characters-in-a-makefile"></a>Derleme Görevleri Dosyasındaki Özel Karakterler
NMAKE özel karakter harf karakter olarak kullanmak için önündeki şapka (^) yerleştirin. NMAKE diğer karakterlerden önce belirliyorsanız düzeltme işaretleri yoksayar. Özel karakterler şunlardır:  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 Tırnak işaretli dize içinde bir şapka (^) değişmez değer düzeltme işareti karakteri olarak kabul edilir. Bir satır sonunda bir şapka bir dize veya makrosu değişmez değer yeni satır karakteri ekler.  
  
 Makrolardaki bir ters eğik çizgi (\\) ve ardından tarafından yeni satır karakteri boşlukla değiştirildi.  
  
 Komutlarda, yüzde simgesi (%) dosya tanımlayıcısı ' dir. % Gerçek anlamda bir komutu temsil etmek için çift yüzde işareti (%) yerine tek bir tane belirtin. Tek bir % NMAKE diğer durumlarda, tam anlamıyla yorumlar, ancak her zaman bir double yorumlar %% tek bir %. Bu nedenle, bir hazır değer temsil etmek için %%, ya da üç yüzde işaretleri belirtin %%%, veya dört yüzde işaretleri %%%.  
  
 Bir komut değişmez değer bir karakteri olarak dolar işareti ($) kullanmak için iki dolar işareti ($$) belirtin. Bu yöntem, diğer durumlarda kullanılabilir olduğu ^ $ çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme görevleri dosyası içeriği](../build/contents-of-a-makefile.md)
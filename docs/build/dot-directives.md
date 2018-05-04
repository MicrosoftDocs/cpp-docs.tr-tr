---
title: Nokta yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29eeedbdc2eaccb753751082a38736fa239837b2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="dot-directives"></a>Nokta Yönergeleri
Nokta yönergeleri bir satır başına bir açıklama bloğundaki dışında belirtin. Nokta yönergeleri noktayla başlayan (. ) ve sonra iki nokta (:) gelmelidir. Alanları ve sekmeler izin verilir. Nokta yönerge adları büyük/küçük harfe duyarlıdır ve büyük harfle yazılır.  
  
|Yönergesi|Amaç|  
|---------------|-------------|  
|**. YOKSAY:**|Derleme görevleri dosyası sonuna belirtilen yerden komutları tarafından döndürülen sıfır olmayan çıkış kodları yok sayar. Varsayılan olarak, bir komutu sıfır olmayan çıkış kodu döndürürse NMAKE durur. Hata denetimi geri yüklemek için kullanmak **! CMDSWITCHES**. Tek bir komut çıkış kodu yoksaymak için tire (-) değiştiricisini kullanın. Dosyanın tamamı için çıkış kodlarını yoksaymak için kullanmak / ediyorum.|  
|**. DEĞERLİ:** *hedefleri*|Korur *hedefleri* bunları güncelleştirmek için komutları durdurulamaz; bir komut dosyası silerek bir kesme işliyorsa disk üzerinde hiçbir etkisi olmaz. Hedef adları bir veya daha fazla boşluk ya da sekme ile ayırın. CTRL + C veya CTRL + BREAK tarafından bir yapı kesintiye uğrarsa varsayılan olarak, bir hedef NMAKE siler. Her kullanımını **. DEĞERLİ** için tüm makefile; geçerlidir birden çok belirtimleri birbirinin yerine kullanılabilir.|  
|**. SESSİZ:**|Derleme görevleri dosyası sonuna belirtilen yerden yürütülen komutların görüntülenmesini engeller. Varsayılan olarak, NMAKE çağırılır komutları görüntüler. Yankı geri yüklemek için kullanmak **! CMDSWITCHES**. Tek bir komutu Yankı gizlemek için kullanın **@** değiştiricisi. Dosyanın tamamı için Yankı gizlemek için kullanın/s'ye.|  
|**. SONEKLERİ:** `list`|Çıkarım kuralı eşleşen uzantılarını listeler; önceden tanımlanmış aşağıdaki uzantıları dahil: .exe .obj .asm .c .cpp .cxx .bas .cbl kullanımına .pas .res .rc .f .f90|  
  
 Değiştirmek için **. SONEKLERİ** listesinde order veya yeni bir liste belirtmek için listeyi temizlemek ve yeni bir ayar belirtin. Listesini temizlemek için iki nokta üst üste sonra hiçbir uzantı belirtin:  
  
```  
.SUFFIXES :  
```  
  
 Listenin sonuna ek sonekleri eklemek için belirtin  
  
```  
.SUFFIXES : suffixlist  
```  
  
 Burada *suffixlist* ek sonekler, bir veya daha fazla boşluk veya sekmeler ayrılmış bir listesi verilmiştir. Geçerli ayarını görmek için **. SONEKLERİ**, parametresini ile NMAKE çalıştırma  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Başvurusu](../build/nmake-reference.md)
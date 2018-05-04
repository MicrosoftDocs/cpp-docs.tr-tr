---
title: Dosya adı parçaları sözdizimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d807087be171a2ad63ed37a8b359c3200c812040
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="filename-parts-syntax"></a>Dosya Adı Parçaları Sözdizimi
Dosya adı parçaları sözdizimi komutlarda bileşenlerini (olabilen bir kapsanan bağımlı) ilk bağımlı dosya adını temsil eder. Disk üzerinde mevcut değil gibi Filename dosyanın sürücü, yol, temel adı ve uzantısı, belirtildiği bileşenleridir. Kullanım **%s** tam dosya adını temsil etmek için. Kullanım **%&#124;**[*bölümleri*]**F** (dikey çubuk karakteri izleyen yüzde simgesi) dosya bölümlerini temsil etmek için burada *bölümleri*sıfır veya daha fazla aşağıdaki harfler, herhangi bir sırada olabilir.  
  
|Harfi|Açıklama|  
|------------|-----------------|  
|Harfi yok|Tam adı (aynı **%s**)|  
|**d**|Sürücü|  
|**p**|Yol|  
|**f**|Temel dosya adı|  
|**e**|Dosya uzantısı|  
  
 Örneğin, dosya adı c:\prog.exe ise:  
  
-   %s c:\prog.exe olur  
  
-   %&#124;F c:\prog.exe olacaktır  
  
-   %&#124;dF c olacaktır  
  
-   %&#124;pF c:\ olacaktır  
  
-   %&#124;fF prog olacaktır  
  
-   %&#124;eF exe olacaktır  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)
---
title: "Dosya adı parçaları sözdizimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a481f8c461cb4fddd4acb090edb2f2b5fd18636d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="filename-parts-syntax"></a>Dosya Adı Parçaları Sözdizimi
Dosya adı parçaları sözdizimi komutlarda bileşenlerini (olabilen bir kapsanan bağımlı) ilk bağımlı dosya adını temsil eder. Disk üzerinde mevcut değil gibi Filename dosyanın sürücü, yol, temel adı ve uzantısı, belirtildiği bileşenleridir. Kullanım **%s** tam dosya adını temsil etmek için. Kullanım **% &#124;** [*bölümleri*]**F** (dikey çubuk karakteri izleyen yüzde simgesi) dosya bölümlerini göstermek için burada *bölümleri* sıfır veya daha fazla aşağıdaki harfleri olabilir herhangi bir sırada.  
  
|Harfi|Açıklama|  
|------------|-----------------|  
|Harfi yok|Tam adı (aynı **%s**)|  
|**d**|Sürücü|  
|**p**|Yol|  
|**f**|Temel dosya adı|  
|**e**|Dosya uzantısı|  
  
 Örneğin, dosya adı c:\prog.exe ise:  
  
-   %s c:\prog.exe olur  
  
-   % &#124; F c:\prog.exe olacaktır  
  
-   % &#124; c olması dF olacaktır  
  
-   % &#124; c:\ olması pF olacaktır  
  
-   % &#124; prog olması fF olacaktır  
  
-   % &#124; exe olması eF olacaktır  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)
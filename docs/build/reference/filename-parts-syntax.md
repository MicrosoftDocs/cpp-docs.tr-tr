---
title: Dosya Adı Parçaları Sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: d5e815dcb8a424d309362e004d1de4c039dc968b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292660"
---
# <a name="filename-parts-syntax"></a>Dosya Adı Parçaları Sözdizimi

Filename-parts söz dizimi komutlarda adının (aynı örtük bir bağımlı olabilir) ilk bağımlı bileşenlerini temsil eder. Diskte yok olarak dosyanın sürücü, yol, temel adı ve uzantısı olarak belirtilen, Filename bileşenleri şunlardır. Kullanım **%s** tam dosya adını göstermek için. Kullanım **%&#124;**[*bölümleri*]**F** (dikey çubuk karakterini izleyen yüzde simgesi) filename parçalarını temsil etmek için burada *bölümleri*sıfır veya daha fazla aşağıdaki harfler, herhangi bir sırada olabilir.

|Harfi|Açıklama|
|------------|-----------------|
|Hiçbir harf|Tam adı (aynı **%s**)|
|**d**|Sürücü|
|**p**|Yol|
|**f**|Dosyası taban adı|
|**e**|Dosya uzantısı|

Örneğin, dosya adı c:\prog.exe ise:

- %s c:\prog.exe olacaktır

- %&#124;F c:\prog.exe olacaktır

- %&#124;dF c olacaktır

- %&#124;pF c:\ olacaktır

- %&#124;fF prog olacaktır

- %&#124;eF exe olacaktır

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyası Komutları](commands-in-a-makefile.md)

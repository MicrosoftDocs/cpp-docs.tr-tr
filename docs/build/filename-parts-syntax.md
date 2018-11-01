---
title: Dosya Adı Parçaları Sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 89869ccaea2a9a5c3d16762fe49b72efc462e0ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552054"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)
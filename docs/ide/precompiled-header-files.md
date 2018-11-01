---
title: Önceden Derlenmiş Üst Bilgi Dosyaları
ms.date: 11/04/2016
f1_keywords:
- stdafx.h
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
ms.openlocfilehash: fed583464aa172887b80a8551adf86e02a76d210
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643215"
---
# <a name="precompiled-header-files"></a>Önceden Derlenmiş Üst Bilgi Dosyaları

Bu dosyaları Ön derlenmiş üstbilgi dosyası oluşturmak için kullanılan *Projname*Stdafx.obj dosya .pch ve önceden derlenmiş türler.

Bu dosyalar bulunur *Projname* dizin. Çözüm Gezgini'nde üst bilgi dosyaları klasöründedir Stdafx.h ve Stdafx.cpp kaynak dosyalar klasöründe bulunur.

|Dosya adı|Açıklama|
|---------------|-----------------|
|Stdafx.h|İçerik dosyası standart sistem ekleme dosyaları için ve sık sık kullanılır, ancak seyrek değiştirilen projeye özgü ekleme dosyaları.<br /><br /> Tanımlayın veya gerekir herhangi stdafx.h _AFX_NO_XXX makroların tanımlarını Kaldır.|
|Stdafx.cpp|Önişlemci yönergesi içeren `#include "stdafx.h"` ve ekler önceden derlenmiş türler için dosyaları ekleme. Önceden derlenmiş dosyalar başlık dosyaları dahil olmak üzere herhangi bir tür, derleme gerektiren dosyaları kısıtlayarak daha hızlı derleme sürelerini destekler. İlk projeniz oluşturulduktan sonra süreleri sonraki sürümlerde önceden derlenmiş üst bilgi dosyalarının varlığı nedeniyle çok daha hızlı derleme fark edeceksiniz.|

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)
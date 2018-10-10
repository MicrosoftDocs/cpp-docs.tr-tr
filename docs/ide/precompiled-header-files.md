---
title: Önceden derlenmiş üst bilgi dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- stdafx.h
dev_langs:
- C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d93486d8df8cdb8bc253a0e71037f4e2ddf9e128
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890485"
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
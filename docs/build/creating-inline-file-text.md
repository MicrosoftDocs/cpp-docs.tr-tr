---
title: Satır içi dosya metni oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce0a345c6c2f48d3d5c2e6fb9d9cfc2a5c03e4ed
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720923"
---
# <a name="creating-inline-file-text"></a>Satır İçi Dosya Metni Oluşturma

Satır içi geçici veya kalıcı dosyalarıdır.

## <a name="syntax"></a>Sözdizimi

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Açıklamalar

Belirtin *inlinetext* komuttan sonra ilk satırda. End çift açılı ayraçlar ile İşaretle (<<) ayrı bir satır başında. Tüm dosya içeren *inlinetext* sınırlandırma köşeli ayraçlar önce. *İnlinetext* makro genişletmeleri ve değişimler, ancak yönergeleri veya derleme görevleri dosyası açıklamaları olabilir. Boşluk, sekme ve yeni satır karakterleri tam anlamıyla kabul edilir.

Geçici bir dosya oturum boyunca var ve diğer komutlar tarafından yeniden kullanılabilir. Belirtin **TUTMAK** NMAKE oturumundan sonra; dosyayı korumak için sağ açılı köşeli sonra isimsiz dosya diskte oluşturulan dosya adı ile korunur. Belirtin **NOKEEP** veya geçici bir dosya için hiçbir şey yok. **TUTUN** ve **NOKEEP** büyük/küçük harfe duyarlı değildir.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](../build/inline-files-in-a-makefile.md)
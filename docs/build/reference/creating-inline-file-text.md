---
title: Satır İçi Dosya Metni Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: a45aa526ca99af93cda86a2a8e0580d4d036ca6d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823524"
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

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](inline-files-in-a-makefile.md)
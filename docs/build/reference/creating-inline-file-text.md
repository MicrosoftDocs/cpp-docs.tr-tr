---
description: 'Hakkında daha fazla bilgi edinin: satır Içi dosya metni oluşturma'
title: Satır İçi Dosya Metni Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: 849273fff4ca0853e4589a38096cbb067c380aae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196860"
---
# <a name="creating-inline-file-text"></a>Satır İçi Dosya Metni Oluşturma

Satır içi dosyalar geçicidir veya kalıcıdır.

## <a name="syntax"></a>Syntax

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Açıklamalar

Komuttan sonraki ilk satırda *ınlinetext* öğesini belirtin. Sonu, ayrı bir satırın başındaki çift açılı ayraçlar (<<) ile işaretleyin. Dosya, sınırlandırma parantezden önceki tüm *ınlinetext* dosyalarını içerir. *Inlinetext* , makro genişletmeleri ve değiştirmeler içerebilir, ancak yönergeleri veya derleme görevleri dosyası açıklamalarını içermez. Boşluklar, sekmeler ve yeni satır karakterleri, tam olarak değerlendirilir.

Oturum süresince geçici bir dosya bulunur ve diğer komutlar tarafından yeniden kullanılabilir. Dosyayı NMAKE oturumundan sonra tutmak için kapanış açılı parantezden sonra **tut** ' i belirtin; adlandırılmamış bir dosya disk üzerinde oluşturulan dosya adı ile korunur. Geçici bir dosya için **nokeep** veya Nothing belirtin. **Keep** ve **nokeep** büyük/küçük harfe duyarlı değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyasındaki satır içi dosyalar](inline-files-in-a-makefile.md)

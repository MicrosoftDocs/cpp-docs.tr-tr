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
ms.openlocfilehash: 3ab1154935ac4eb8b0595c84ba8d75a9ca13e4d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="creating-inline-file-text"></a>Satır İçi Dosya Metni Oluşturma
Satır içi dosyalar, geçici veya kalıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtin *inlinetext* komutu sonra ilk satırdaki. Çift köşeli parantez ile biten işaretlemek (<<) ayrı bir satır başında. Tüm dosya içeren *inlinetext* sınırlandırma köşeli önce. *İnlinetext* makrosu uzantılarına ve kısaltmaları, ancak yönergeleri veya derleme görevleri dosyası açıklamaları olabilir. Boşluk, sekme ve yeni satır karakterlerini tam anlamıyla kabul edilir.  
  
 Geçici bir dosya oturum boyunca var ve diğer komutlarla yeniden kullanılabilir. Belirtin **TUTMAK** NMAKE oturumun ardından; dosyayı korumak için kapanış açılı ayraçları sonra adsız bir dosya diskte oluşturulan dosya adı ile korunur. Belirtin **NOKEEP** veya geçici bir dosya için hiçbir şey yok. **TUTMAK** ve **NOKEEP** büyük küçük harfe duyarlı değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](../build/inline-files-in-a-makefile.md)
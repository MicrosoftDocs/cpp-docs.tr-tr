---
title: "Satır içi dosya metni oluşturma | Microsoft Docs"
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
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dcc27a303e9d03d2e899a76703bcfae5abfd0c04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
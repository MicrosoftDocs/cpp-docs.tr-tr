---
title: "Geriye dönük uyumluluk | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.programs
dev_langs: C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 341dc7f2b16449356fab60f79424f5031ceefd6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk
Ürün sürümleri, OLDNAMES kitaplığı arasındaki uyumluluk için. LIB yeni adlarına eski adlarını eşler. Örneğin, `open` eşlendiği `_open`. Açıkça OLDNAMES ile bağlamanız gerekir. Yalnızca komut satırı seçenekleri aşağıdaki birleşimlerine derlediğinizde LIB:  
  
-   `/Zl`(nesne dosyasından varsayılan kitaplık adını atla) ve `/Ze` (varsayılan — Microsoft uzantıları kullanma)  
  
-   `/link`(Bağlayıcı-denetimi) `/NOD` (hiçbir varsayılan kitaplık arama) ve`/Ze`  
  
 Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz: [derleyici başvurusu](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)
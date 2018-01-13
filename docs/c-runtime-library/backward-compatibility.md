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
ms.workload: cplusplus
ms.openlocfilehash: a8ffcc5ab1f50c474ed0ecf4d014419111682b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk
Ürün sürümleri, OLDNAMES kitaplığı arasındaki uyumluluk için. LIB yeni adlarına eski adlarını eşler. Örneğin, `open` eşlendiği `_open`. Açıkça OLDNAMES ile bağlamanız gerekir. Yalnızca komut satırı seçenekleri aşağıdaki birleşimlerine derlediğinizde LIB:  
  
-   `/Zl`(nesne dosyasından varsayılan kitaplık adını atla) ve `/Ze` (varsayılan — Microsoft uzantıları kullanma)  
  
-   `/link`(Bağlayıcı-denetimi) `/NOD` (hiçbir varsayılan kitaplık arama) ve`/Ze`  
  
 Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz: [derleyici başvurusu](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)
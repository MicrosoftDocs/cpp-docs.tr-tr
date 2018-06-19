---
title: Geriye dönük uyumluluk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9a04dec046435478ca621ad8f5e2e3c4323f3e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386244"
---
# <a name="backward-compatibility"></a>Geriye Dönük Uyumluluk
Ürün sürümleri, OLDNAMES kitaplığı arasındaki uyumluluk için. LIB yeni adlarına eski adlarını eşler. Örneğin, `open` eşlendiği `_open`. Açıkça OLDNAMES ile bağlamanız gerekir. Yalnızca komut satırı seçenekleri aşağıdaki birleşimlerine derlediğinizde LIB:  
  
-   `/Zl` (nesne dosyasından varsayılan kitaplık adını atla) ve `/Ze` (varsayılan — Microsoft uzantıları kullanma)  
  
-   `/link` (Bağlayıcı-denetimi) `/NOD` (hiçbir varsayılan kitaplık arama) ve `/Ze`  
  
 Derleyici komut satırı seçenekleri hakkında daha fazla bilgi için bkz: [derleyici başvurusu](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uyumluluk](../c-runtime-library/compatibility.md)
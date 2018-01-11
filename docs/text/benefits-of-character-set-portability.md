---
title: "Karakter yararları taşınabilirlik ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554137352c0a8f7275a051e4026020fce25edbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-of-character-set-portability"></a>Karakter Kümesi Taşınabilirliğinin Yararları
Şu anda uygulamanızı amaçlamasanız istemediğiniz olsa bile MFC ve C çalışma zamanı taşınabilirlik özellikleri kullanarak yararlı olabilir:  
  
-   Temelinizi kodlama kodunuzu temel esnek hale getirir. Daha sonra kolayca Unicode ya da MBCS taşıma.  
  
-   Unicode kullanarak Windows 2000 için uygulamalarınızı daha verimli hale getirir. Windows 2000 Unicode kullandığı için ve işletim sisteminden geçirilen Unicode olmayan dizeler, da ek yüke neden çevrilmesi gerekir.  
  
-   MBCS kullanarak Windows 95 gibi Windows 2000 veya Windows 98 dışında Win32 platformlarında uluslararası pazarda desteklemenize olanak tanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)   
 [Unicode Desteği](../text/support-for-unicode.md)
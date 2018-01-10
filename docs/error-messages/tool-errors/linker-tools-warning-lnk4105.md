---
title: "Bağlayıcı araçları uyarısı LNK4105 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4105
dev_langs: C++
helpviewer_keywords: LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 913a6da056908def8df5aab1c2425ef9a187c1e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4105"></a>Bağlayıcı Araçları Uyarısı LNK4105
bağımsız değişken 'seçeneği'; seçeneğiyle belirtilmedi seçeneği yoksayılıyor  
  
 Bu uyarı, yalnızca oluşur zaman [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği ayarlanmış. Bu seçenek ile hiçbir dizin belirtilirse, bağlayıcı seçeneği yoksayar ve bu uyarı iletisi oluşturur.  
  
 Varolan ortam kitaplığı ayarlarını geçersiz kılmak üzere gerekmiyorsa bağlayıcı komut satırından/Libpath seçeneğini kaldırın. Alternatif arama yolu kitaplıkları için kullanmak istiyorsanız, / Libpath seçenekten alternatif yolu belirtin.  
  
## <a name="example"></a>Örnek  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 gerekli kitaplıklarında aramak için bağlayıcı yönlendirir `c:\filepath\lib` varsayılan konumlarda arama önce.
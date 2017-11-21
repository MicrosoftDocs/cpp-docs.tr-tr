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
ms.openlocfilehash: d64ff3756f709820c7e25b2986b8529a364139e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
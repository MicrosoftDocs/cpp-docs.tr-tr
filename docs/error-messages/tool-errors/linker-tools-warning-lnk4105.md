---
title: Bağlayıcı araçları uyarısı LNK4105 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffdd8953e08f38d36bdfc2e68ad6cb8e06fb85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33304420"
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
---
title: Yapı içi değerler ve satır içi derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff2b99eedcdd81a96dc3091046a4f62ffe002509
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465998"
---
# <a name="intrinsics-and-inline-assembly"></a>Yapı İçi Değerler ve Satır İçi Derleme
Bir x64 için kısıtlamaların derleyici satır içi assembler desteği yok etmektir. İşlevler yani C veya C++ ortamında ya da alt yordamlar veya derleyici tarafından desteklenen iç işlevleri olarak yazılması gerekir yazılamaz. Diğerleri oluşturulmazken belirli performans duyarlı işlevlerdir. Performans açısından duyarlı işlevleri, iç işlev olarak uygulanmalıdır.  
  
 Derleyici tarafından desteklenen yapı içlerini açıklanan [derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 Yazılım Kuralları](../build/x64-software-conventions.md)
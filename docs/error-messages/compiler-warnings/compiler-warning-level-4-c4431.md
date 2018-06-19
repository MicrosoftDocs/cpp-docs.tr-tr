---
title: Derleyici Uyarısı (düzey 4) C4431 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4431
dev_langs:
- C++
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bb5a76a1ddf1f1104fe88511c9bf9bf88bf6602
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292262"
---
# <a name="compiler-warning-level-4-c4431"></a>Derleyici Uyarısı (düzey 4) C4431
tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor  
  
 Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda oluşturulabilir: Visual C++ artık oluşturur türsüz tanımlayıcıları olarak int varsayılan olarak. Tanımlayıcı türü açıkça belirtilmesi gerekir.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4431 oluşturur.  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```
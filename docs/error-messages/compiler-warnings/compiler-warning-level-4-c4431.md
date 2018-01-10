---
title: "Derleyici Uyarısı (düzey 4) C4431 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4431
dev_langs: C++
helpviewer_keywords: C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6594d50cf3688565bc2570ba536ddb908c482f23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
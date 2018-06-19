---
title: Derleyici Uyarısı (düzey 1) C4716 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4716
dev_langs:
- C++
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be620264c315fc9c2ff3cd4cb91bd9d77c8a4d07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288859"
---
# <a name="compiler-warning-level-1-c4716"></a>Derleyici Uyarısı (düzey 1) C4716
'function' bir değer döndürmesi gerekir  
  
 Verilen işlevin bir değer döndürmedi.  
  
 Yalnızca işlevler bir dönüş türü void can ile eşlik eden bir dönüş değeri olmadan dönüş komutunu kullanın.  
  
 Bu işlev çağrıldığında tanımlanmamış bir değere döndürülür.  
  
 Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md).  
  
 Aşağıdaki örnek C4716 oluşturur:  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```
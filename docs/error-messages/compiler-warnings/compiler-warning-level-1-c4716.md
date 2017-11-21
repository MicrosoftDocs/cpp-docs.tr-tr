---
title: "Derleyici Uyarısı (düzey 1) C4716 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4716
dev_langs: C++
helpviewer_keywords: C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d8ded9465251b5c9f0adddbebe1738fa519097c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
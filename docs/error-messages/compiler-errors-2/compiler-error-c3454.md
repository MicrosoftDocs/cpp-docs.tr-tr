---
title: "Derleyici Hatası C3454 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3454
dev_langs: C++
helpviewer_keywords: C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 026b77ca4f9488c1178a2815ffb0a9c7c71bdf54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3454"></a>Derleyici Hatası C3454
[öznitelik] sınıfı bildiriminde izin verilmiyor  
  
 Bir sınıf bir özniteliği için tanımlanmalıdır.  
  
 Daha fazla bilgi için bkz: [özniteliği](../../windows/attribute.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3454 oluşturur.  
  
```  
// C3454.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute]   // C3454  
ref class Attr1;  
  
[attribute]   // OK  
ref class Attr2 {};  
```
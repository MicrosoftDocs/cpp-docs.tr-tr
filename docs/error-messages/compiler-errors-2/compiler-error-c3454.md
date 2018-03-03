---
title: "Derleyici Hatası C3454 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 42a685d7084f5edd2a3f6b2fe6f1ab9d83e9c18f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
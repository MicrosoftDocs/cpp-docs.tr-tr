---
title: "Derleyici Hatası C2364 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2364
dev_langs: C++
helpviewer_keywords: C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d7c5042d4b5984a87b52cefafd1f591ec662ab48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2364"></a>Derleyici Hatası C2364
'type': özel özniteliği için geçersiz tür  
  
 Özel öznitelikler için adlandırılmış bağımsız değişkenler zamanı sabitleri derlemek için sınırlıdır. Örneğin, tam sayı türleri (int, char, vb.) System::Type ^ ve System::Object ^.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2364 oluşturur.  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```
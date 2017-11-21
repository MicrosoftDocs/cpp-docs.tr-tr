---
title: "Derleyici Uyarısı (Düzey 3) C4580 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4580
dev_langs: C++
helpviewer_keywords: C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a8dae06450227f6739f12d7c55684b171d103377
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4580"></a>Derleyici Uyarısı (Düzey 3) C4580
[öznitelik] kullanım dışıdır; Bunun yerine bir temel sınıf olarak System::Attribute veya Platform::Metadata belirtin  
  
[[özniteliği](../../windows/attribute.md)] artık kullanıcı tanımlı öznitelikler oluşturmak için tercih edilen sözdizimi aşağıdaki gibidir. Daha fazla bilgi için bkz: [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md). CLR kodunu özniteliklerden türetilen `System::Attribute`. Windows çalışma zamanı kodunu özniteliklerden türetilen `Platform::Metadata`.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3454 oluşturur ve nasıl düzeltileceği gösterir.  
  
```cpp  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```
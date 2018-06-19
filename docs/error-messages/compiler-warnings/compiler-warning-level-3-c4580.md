---
title: Derleyici Uyarısı (Düzey 3) C4580 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89ad08af77b62cd0992e9415e2df8b31233e4e0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290988"
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
---
title: Derleyici Hatası C3099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27059beb1cb587b9060da8c5cc5702ea966422f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249761"
---
# <a name="compiler-error-c3099"></a>Derleyici Hatası C3099
'anahtar sözcüğü': [System::AttributeUsageAttribute] yönetilen özniteliklerini; kullanın [Windows::Foundation::Metadata::AttributeUsageAttribute] WinRT öznitelikleri için kullanın  
  
 Kullanım <xref:System.AttributeUsageAttribute> bildirmek için **/CLR** öznitelikleri. Kullanım `Windows::Foundation::Metadata::AttributeUsageAttribute` Windows çalışma zamanı öznitelikleri bildirmek için.  
  
 / CLR öznitelikleri hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md). Windows çalışma zamanı desteklenen öznitelikleri için bkz: [Windows.Foundation.Metadata ad alanı](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3099 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```
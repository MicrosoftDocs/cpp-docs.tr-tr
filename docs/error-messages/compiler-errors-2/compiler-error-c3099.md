---
title: "Derleyici Hatası C3099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3099
dev_langs: C++
helpviewer_keywords: C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a644a27c834efcd3c3857241927a6e618f600d0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
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
ms.openlocfilehash: ea57a79fab92152824b7c9aaf0c5d50c14fee32e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212001"
---
# <a name="compiler-error-c3099"></a>Derleyici Hatası C3099
'anahtar sözcüğü': [System::AttributeUsageAttribute] yönetilen öznitelikleri için; kullanın. [Windows::Foundation::Metadata::AttributeUsageAttribute] WinRT öznitelikleri için kullanın.  
  
 Kullanım <xref:System.AttributeUsageAttribute> bildirmek için **/CLR** öznitelikleri. Kullanım `Windows::Foundation::Metadata::AttributeUsageAttribute` Windows çalışma zamanı öznitelik bildirmek için.  
  
 / CLR öznitelikleri hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md). Windows çalışma zamanı için desteklenen öznitelik [Windows.Foundation.Metadata ad alanı](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, C3099 oluşturur ve bu sorunun nasıl gösterir.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```
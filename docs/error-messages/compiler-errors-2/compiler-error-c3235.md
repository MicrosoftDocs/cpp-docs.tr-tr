---
title: Derleyici Hatası C3235 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3235
dev_langs:
- C++
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6101d6f3d15e0276697130f26627ced593fef0a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252251"
---
# <a name="compiler-error-c3235"></a>Derleyici Hatası C3235
'uzmanlık': genel bir sınıf açık ya da kısmi uzmanlığı izin verilmiyor  
  
 Genel sınıflar açık ya da kısmi özelleştirmeleri için kullanılamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3235 oluşturur.  
  
```  
// C3235.cpp  
// compile with: /clr  
generic<class T>  
public ref class C {};  
  
generic<>  
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.  
```
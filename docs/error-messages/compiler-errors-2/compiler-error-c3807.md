---
title: Derleyici Hatası C3807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3807
dev_langs:
- C++
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4171b13d7605d296ac8ac6d1f06125d0fadd226
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272324"
---
# <a name="compiler-error-c3807"></a>Derleyici Hatası C3807
'type': 'type2' bir sınıf ComImport özniteliğine sahip türetilemez, yalnızca arabirim uygulamasına izin verilir  
  
 Türetilen bir tür <xref:System.Runtime.InteropServices.ComImportAttribute> yalnızca bir arabirimi uygulayabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3807 oluşturur.  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```
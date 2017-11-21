---
title: "Derleyici Hatası C3393 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3393
dev_langs: C++
helpviewer_keywords: C3393
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d123bde1de2eff97b3ae9facfca1a200d278c6f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3393"></a>Derleyici Hatası C3393
kısıtlaması yan tümcesinde sözdizimi hatası: 'tanımlayıcısı' türünde değil  
  
 Bir tür olmalıdır, bir kısıtlama olarak geçirilen tanımlayıcı bir türde değildi.  Daha fazla bilgi için bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3393 oluşturur:  
  
```  
// C3393.cpp  
// compile with: /clr /c  
void MyInterface() {}  
interface class MyInterface2 {};  
  
generic<typename T>  
where T : MyInterface   // C3393  
// try the following line instead  
// where T : MyInterface2  
ref class R {};  
```
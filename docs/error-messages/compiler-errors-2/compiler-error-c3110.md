---
title: "Derleyici Hatası C3110 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3110
dev_langs: C++
helpviewer_keywords: C3110
ms.assetid: 821dc71f-896e-4b2d-af0e-aa9932934b7b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 573b7bbbe40929d291c10426e7826293e8dfd4bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3110"></a>Derleyici Hatası C3110
'işlev_adı': COM arabirimi yöntemi aşırı yükleme  
  
 Bir arabirim özniteliği tarafından gibi başında bir arabirim:  
  
-   [Özel](../../windows/custom-cpp.md)  
  
-   [görüntüleme arabirimi](../../windows/dispinterface.md)  
  
-   [çift](../../windows/dual.md)  
  
-   [Nesne](../../windows/object-cpp.md)  
  
 aşırı yüklenemez. Örneğin:  
  
```  
// C3110.cpp  
#include <unknwn.h>  
[ object, uuid= "4F98A180-EF37-11D1-978D-0000F805D73B" ]  
__interface ITestInterface  
{  
   HRESULT mf1(void);  
   HRESULT mf1(BSTR); // C3110  
};  
  
int main()  
{  
}  
```
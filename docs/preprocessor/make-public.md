---
title: make_public | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e4e6f96c1b794c71cf6f3ce97600583e88d52b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="makepublic"></a>make_public
Yerel tür genel birleştirme erişilebilirlik olması gerektiğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma make_public(type)  
```  
  
### <a name="parameters"></a>Parametreler  
 `type`genel derleme erişilebilirlik sahip yapmak istediğiniz kaynak türünü adıdır.  
  
## <a name="remarks"></a>Açıklamalar  
`make_public`başvuru yapmak istediğinizi yerel tür değiştiremezsiniz .h dosyasından olduğunda için yararlıdır. Genel derleme bir görünürlük türü ortak bir işlevde imzada yerel tür kullanmak istiyorsanız, derleyici bir uyarı verecek veya yerel tür ayrıca genel derleme erişilebilirlik olmalıdır.  
  
`make_public`Genel kapsamda belirtilmeli ve yalnızca noktasından etkisi hangi BT aracılığıyla kaynak kodu dosyasının sonuna bildirilmiş bulunmaktadır.  
  
Yerel türü örtük veya açık olarak özel olabilir; bkz: [tür görünürlüğü](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek, iki yerel yapılar için tanımları içeren bir .h dosyasının içeriğidir.  
  
```cpp  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## <a name="example"></a>Örnek  
Aşağıdaki kod örneği üstbilgi dosyası tüketir ve açıkça kullanarak yerel yapılar ortak olarak işaretlemek sürece gösterir `make_public`, yerel yapılar ortak işlevinde imza kullanmaya çalıştığınızda derleyici bir uyarı oluşturur bir Ortak yönetilen türü.  
  
```cpp  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
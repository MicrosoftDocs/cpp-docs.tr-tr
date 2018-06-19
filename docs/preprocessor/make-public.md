---
title: make_public | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27db5ac934973178e2485327090ed70f994becec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849593"
---
# <a name="makepublic"></a>make_public
Yerel tür genel birleştirme erişilebilirlik olması gerektiğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma make_public(type)  
```  
  
### <a name="parameters"></a>Parametreler  
 `type` genel derleme erişilebilirlik sahip yapmak istediğiniz kaynak türünü adıdır.  
  
## <a name="remarks"></a>Açıklamalar  
`make_public` başvuru yapmak istediğinizi yerel tür değiştiremezsiniz .h dosyasından olduğunda için yararlıdır. Genel derleme bir görünürlük türü ortak bir işlevde imzada yerel tür kullanmak istiyorsanız, derleyici bir uyarı verecek veya yerel tür ayrıca genel derleme erişilebilirlik olmalıdır.  
  
`make_public` Genel kapsamda belirtilmeli ve yalnızca noktasından etkisi hangi BT aracılığıyla kaynak kodu dosyasının sonuna bildirilmiş bulunmaktadır.  
  
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
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
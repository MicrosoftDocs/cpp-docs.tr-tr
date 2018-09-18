---
title: Lock::operator == | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock::operator==
- msclr.lock.operator==
- msclr::lock::operator==
- lock.operator==
dev_langs:
- C++
helpviewer_keywords:
- lock::operator==
ms.assetid: 3dcf1e5a-53fc-495d-9df5-d7849a41c36c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 38cefb80b1c4c6969cba976c30383c1499a4968d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048896"
---
# <a name="lockoperator"></a>lock::operator==
Eşitlik işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class T> bool operator==(  
   T t  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*T*<br/>
Eşitlik için karşılaştırma yapılacak nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `true` varsa `t` kilit ait nesne aynı `false` Aksi takdirde.  
  
## <a name="example"></a>Örnek  
  
```  
// msl_lock_op_eq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   lock l1(o1);  
   if (l1 == o1) {  
      Console::WriteLine("Equal!");  
   }  
}  
```  
  
```Output  
Equal!  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi dosyası** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [lock üyeleri](../dotnet/lock-members.md)   
 [lock::operator!=](../dotnet/lock-operator-inequality.md)
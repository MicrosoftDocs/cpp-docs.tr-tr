---
title: Derleyici Hatası C3706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3706
dev_langs:
- C++
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cb54dfce6a6974fcf09886f2d13047cdab53ced
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265252"
---
# <a name="compiler-error-c3706"></a>Derleyici Hatası C3706
'function': COM olayları tetiklenecek COM arabirimi olmalıdır  
  
 COM olayları tetiklenecek kullandığınız olay arabirimi COM arabirimi olması gerekir. Bu durumda, arabirimi kullanarak bir Visual C++ öznitelik ya da tanımlanmalıdır veya kullanılarak içe [#import](../../preprocessor/hash-import-directive-cpp.md) #import's embedded_idl özniteliği olan tür kitaplığından.  
  
 Unutmayın `#include` COM olayları kullanmak için örnekte gösterildiği ATL üstbilgi dosyaları satırlık gereklidir. Bu hatayı düzeltmek için olun `IEvents` (olay arabirimi) aşağıdakilerden birini uygulayarak COM arabirimi arabirim tanımı öznitelikleri: [nesne](../../windows/object-cpp.md), [çift](../../windows/dual.md), veya [ görüntüleme arabirimi](../../windows/dispinterface.md).  
  
 Arabirim MIDL tarafından oluşturulan bir üstbilgi dosyası ise, derleyici COM arabirimi olarak bunu tanımaz.  
  
 Aşağıdaki örnek C3706 oluşturur:  
  
```  
// C3706.cpp  
// compile with: /c  
// C3706 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following line to resolve.  
// [object, uuid="12341234-1234-1234-1234-123412341237"]  
__interface IEvents : IUnknown {  
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]  
};  
  
[dual, uuid="12341234-1234-1234-1234-123412341235"]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]  
class CEventSrc : public IBase {  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```
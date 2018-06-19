---
title: Derleyici Uyarısı (düzey 1) C4692 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4692
dev_langs:
- C++
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a908aae7e561f78514cda1f31b78060ce88d90ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285661"
---
# <a name="compiler-warning-level-1-c4692"></a>Derleyici Uyarısı (düzey 1) C4692
'function': özel olmayan üyenin imzası 'native_type' derleme özel yerel türünü içeriyor  
  
 Derlemenin dışından görünür olan bir türü derlemenin dışından görünür değil yerel bir tür olan imza içeren bir üye işlevi içerir. Bu nedenle, içeren türde derlemenin dışından örneği varsa üye fonksiyonu çağrılmamalıdır.  
  
 Daha fazla bilgi için bkz: [yazın görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).  
  
 Varsayılan olarak bu uyarı kapalıdır. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4692 oluşturur.  
  
```  
// C4692.cpp  
// compile with: /W1 /c /clr  
#pragma warning(default:4692)  
class Private_Native_Class {};  
public class Public_Native_Class {};  
public ref class Public_Ref_Class {  
public:  
   void Test(Private_Native_Class *) {}   // C4692  
   void Test2(Public_Native_Class *) {}   // OK  
};  
```
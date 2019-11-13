---
title: Derleyici Uyarısı (düzey 1) C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: e7ec657956c72f1e321227d54b796164292f0c0e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052491"
---
# <a name="compiler-warning-level-1-c4692"></a>Derleyici Uyarısı (düzey 1) C4692

'function': özel olmayan üyenin imzası 'native_type' derleme özel yerel türünü içeriyor

Derlemenin dışında görünen bir tür, imzası, derlemenin dışında görünmeyen yerel bir tür içeren bir üye işlevi içerir. Bu nedenle, üye işlevi, kapsayan türü derlemenin dışında örneği oluşturulmuş ise çağrılmamalıdır.

Daha fazla bilgi için bkz. [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4692 oluşturur.

```cpp
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
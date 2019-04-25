---
title: Derleyici Uyarısı (düzey 1) C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: d013990d0d56c028f48928d1b48c2e0a66b393af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221272"
---
# <a name="compiler-warning-level-1-c4692"></a>Derleyici Uyarısı (düzey 1) C4692

'function': özel olmayan üyenin imzası 'native_type' derleme özel yerel türünü içeriyor

Bir üye işlev imzası olan, derlemenin dışında görünür olmayan yerel bir tür içeren derlemenin dışında görünür olan bir türü içerir. Bu nedenle, derlemenin dışından kapsayan türü örneği varsa üye işlevi çağrılmamalıdır.

Daha fazla bilgi için [türü görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

Varsayılan olarak bu uyarıyı kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4692 oluşturur.

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
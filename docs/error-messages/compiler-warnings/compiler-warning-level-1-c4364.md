---
title: Derleyici Uyarısı (düzey 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 5423a5525f9bef4d949bfee2de058fe19d0ec181
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220047"
---
# <a name="compiler-warning-level-1-c4364"></a>Derleyici Uyarısı (düzey 1) C4364

\#daha önce as_friend özniteliği olmadan konumunda (line_number) görülen ' dosya ' derlemesi için kullanılıyor; as_friend uygulanmadı

`#using`Belirtilen meta veri dosyası için bir yönerge tekrarlandı, ancak **`as_friend`** niteleyici ilk oluşumda kullanılmadı; derleyici ikincisini yoksayacak **`as_friend`** .

Daha fazla bilgi için bkz. [arkadaş derlemeler (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C4364 oluşturur.

```cpp
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```

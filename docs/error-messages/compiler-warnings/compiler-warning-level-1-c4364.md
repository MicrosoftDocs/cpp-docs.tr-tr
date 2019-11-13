---
title: Derleyici Uyarısı (düzey 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 716f440cddc3889ec719ef3b295a0d076175be93
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966527"
---
# <a name="compiler-warning-level-1-c4364"></a>Derleyici Uyarısı (düzey 1) C4364

\#, daha önce as_friend özniteliği olmadan konumda (line_number) görülen ' dosya ' derlemesi için kullanılıyor; as_friend uygulanmadı

Verilen bir meta veri dosyası için bir `#using` yönergesi tekrarlandı, ancak `as_friend` niteleyicisi ilk oluşumda kullanılmadı; Derleyici ikinci `as_friend`yoksayacaktır.

Daha fazla bilgi için bkz. [arkadaş derlemelerC++()](../../dotnet/friend-assemblies-cpp.md).

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
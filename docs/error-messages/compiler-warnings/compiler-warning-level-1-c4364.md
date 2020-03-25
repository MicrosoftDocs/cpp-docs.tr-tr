---
title: Derleyici Uyarısı (düzey 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 79c8809b4de9d6853aaacec4283bf01d0e89305e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187108"
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

---
title: Derleyici Uyarısı (düzey 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: 56fe0f314142d873fc02136bc2c3fe65e71f4dda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544072"
---
# <a name="compiler-warning-level-1-c4399"></a>Derleyici Uyarısı (düzey 1) C4399

> '*sembol*': işlem içi simge/CLR ile derlendiğinde __declspec(dllimport) ile işaretlenmemelidir: Saf

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Yerel bir görüntü veya görüntü ile yerel ve CLR yapıları saf bir görüntüye içeri aktarılamıyor. Bu uyarıyı çözmek için derleme **/CLR** (değil **/CLR: pure**) veya silme `__declspec(dllimport)`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4399 oluşturur.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
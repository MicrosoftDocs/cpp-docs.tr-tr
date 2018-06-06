---
title: Derleyici Uyarısı (düzey 1) C4399 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aedad6aed07a6056f74ad338037a7268c722627f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703726"
---
# <a name="compiler-warning-level-1-c4399"></a>Derleyici Uyarısı (düzey 1) C4399

> '*sembol*': işlem içi simgesi işaretlenmemiş/CLR ile derlendiğinde __declspec(dllimport) ile: Saf

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Yerel görüntü veya yerel ve CLR yapılarına görüntüyle verileri saf görüntüsüne alınamıyor. İle bu uyarıyı çözmek için derleme **/CLR** (değil **/CLR: pure**) veya silme `__declspec(dllimport)`.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4399 oluşturur.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
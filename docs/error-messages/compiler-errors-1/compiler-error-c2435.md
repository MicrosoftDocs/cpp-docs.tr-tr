---
title: Derleyici hatası C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: 7ef22711884dabb83efa8c7ebfdb7648316c12ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205419"
---
# <a name="compiler-error-c2435"></a>Derleyici hatası C2435

> '*var*': dinamik başlatma yönetilen CRT gerektirir;/clr: Safe ile derlenemez

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Global uygulama başına etki alanı değişkeninin başlatılması, doğrulanabilir bir görüntü üretmeyen `/clr:pure`ile derlenmiş CRT gerektirir.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [Process](../../cpp/process.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2435 oluşturur:

```cpp
// C2435.cpp
// compile with: /clr:safe /c
int globalvar = 0;   // C2435

__declspec(process)
int globalvar2 = 0;
```

---
title: Derleyici Hatası C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: 5cd7a83575da7ab2a30401406d0c2ccf6c1b603e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166652"
---
# <a name="compiler-error-c2435"></a>Derleyici Hatası C2435

> '*var*': dinamik başlatma yönetilen CRT gerektirir; / CLR: safe ile derlenemez

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Genel uygulama başına etki alanı değişkenini, başlatma ile derlenmiş CRT gerektirir `/clr:pure`, doğrulanabilir bir görüntü oluşturmuyor.

Daha fazla bilgi için [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2435 oluşturur:

```cpp
// C2435.cpp
// compile with: /clr:safe /c
int globalvar = 0;   // C2435

__declspec(process)
int globalvar2 = 0;
```
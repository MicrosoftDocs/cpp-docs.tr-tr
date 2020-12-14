---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2435'
title: Derleyici hatası C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: d0ab5d8c7c45c9636a5e48acc17d3ac379c755a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189944"
---
# <a name="compiler-error-c2435"></a>Derleyici hatası C2435

> '*var*': dinamik başlatma yönetilen CRT gerektirir;/clr: Safe ile derlenemez

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Global uygulama başına etki alanı değişkeninin başlatılması için `/clr:pure` , doğrulanabilen bir görüntü üreten CRT ile derlenmiş.

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

---
title: Derleyici Hatası C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: eda3910c99f4c8ea96568f2d475c5d6a1e4cdc7c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041052"
---
# <a name="compiler-error-c3163"></a>Derleyici Hatası C3163

'oluşturmak': öznitelikler önceki bildirimle tutarsız

Bir bildirimi için uygulanan öznitelikleri bir tanımına uygulanan öznitelikleri çakışıyor.

İleri dönük bildirimi özniteliklerinde ortadan kaldırmak için C3163 çözmenin bir yolu var. İleri dönük bildiriminin üzerinde herhangi bir özniteliği tanımı özniteliklerinde değerinden küçük olması veya en fazla onlara eşit.

C3163 hatanın olası nedeni, Microsoft kaynak kodu ek açıklama dili (SAL) içerir. SAL makroları kullanarak projenizi derleme sürece genişletmeyin **/ analyze** bayrağı. İle yeniden derlemeniz denerseniz, bir program olan olmadan düzgün bir şekilde derlendiğinden / analyze C3163 fırlatabilir / analyze seçeneği. SAL hakkında daha fazla bilgi için bkz: [SAL ek açıklamalarını](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3163 oluşturur.

```
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>Ayrıca bkz.

[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)
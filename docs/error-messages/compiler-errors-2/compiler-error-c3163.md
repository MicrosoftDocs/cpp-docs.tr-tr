---
title: Derleyici Hatası C3163 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e712a70bdd443d9a6c640853b958f29dac78dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061974"
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

## <a name="see-also"></a>Ayrıca Bkz.

[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)
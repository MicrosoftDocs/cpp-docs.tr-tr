---
title: Derleyici Uyarısı C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 50551faf817f83d8a4af848a75af67ebe7004fe7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635490"
---
# <a name="compiler-warning-c4687"></a>Derleyici Uyarısı C4687

'class': kapalı bir soyut sınıf 'interface' bir arabirim uygulayamaz

Korumalı, soyut bir tür genellikle yalnızca statik üye işlevleri kullanışlıdır.

Daha fazla bilgi için [soyut](../../windows/abstract-cpp-component-extensions.md)ve [korumalı](../../windows/sealed-cpp-component-extensions.md).

C4687, varsayılan bir hata verilir. İle C4687 gizleyebilirsiniz [uyarı](../../preprocessor/warning.md) pragması. Korumalı, soyut bir tür içinde arabirim uygulamak istediğinizden eminseniz, C4687 gösterilmemesini sağlayabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4687 oluşturur.

```
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```
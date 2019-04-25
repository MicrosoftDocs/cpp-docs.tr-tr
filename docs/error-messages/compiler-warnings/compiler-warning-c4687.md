---
title: Derleyici Uyarısı C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: 1978e1a35ba5b5d59b5961a21378d8af6921d145
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311338"
---
# <a name="compiler-warning-c4687"></a>Derleyici Uyarısı C4687

'class': kapalı bir soyut sınıf 'interface' bir arabirim uygulayamaz

Korumalı, soyut bir tür genellikle yalnızca statik üye işlevleri kullanışlıdır.

Daha fazla bilgi için [soyut](../../extensions/abstract-cpp-component-extensions.md)ve [korumalı](../../extensions/sealed-cpp-component-extensions.md).

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
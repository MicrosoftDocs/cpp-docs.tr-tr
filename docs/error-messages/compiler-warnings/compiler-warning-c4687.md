---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4687'
title: Derleyici Uyarısı C4687
ms.date: 11/04/2016
f1_keywords:
- C4687
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
ms.openlocfilehash: ffa8e645aa82a8577d0cd39a4963b8008b6cf9a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180727"
---
# <a name="compiler-warning-c4687"></a>Derleyici Uyarısı C4687

> '*Class*': kapalı bir soyut sınıf '*Interface*' arabirimini uygulayamaz

## <a name="remarks"></a>Açıklamalar

Sealed, soyut bir tür genellikle yalnızca statik üye işlevlerini tutmak için faydalıdır.

Daha fazla bilgi için bkz. [soyut](../../extensions/abstract-cpp-component-extensions.md) ve [korumalı](../../extensions/sealed-cpp-component-extensions.md).

C4687, varsayılan olarak bir hata olarak verilir. [Uyarı](../../preprocessor/warning.md) pragması ile C4687 ' i gizleyebilirsiniz. Korumalı, soyut bir türde bir arabirim uygulamak istediğinizden eminseniz C4687 'i gizleyebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4687 oluşturur.

```cpp
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```

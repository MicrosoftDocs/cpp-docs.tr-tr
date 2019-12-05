---
title: Derleyici Uyarısı C4577
description: Derleyici Uyarısı C4577 açıklaması ve çözümü.
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: e29e47b2a268d86f7f6a280b79a1604fe6eff8a4
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810563"
---
# <a name="compiler-warning-level-1-c4577"></a>Derleyici Uyarısı (düzey 1) C4577

> ' noexcept ', özel durum işleme modu belirtilmediği için kullanıldı; özel durum üzerinde sonlandırma garanti edilmez. /EHsc belirtin

Derleyici bir `noexcept` belirtimi algıladı, ancak standart C++ özel durum işleme belirtilmedi. Derleyici, C++ [/EHsc](../../build/reference/eh-exception-handling-model.md) derleyici seçeneği belirtilmediği takdirde standart olarak özel durum işlemesini tam olarak desteklemez. Bu sorunu çözmek için **/EHsc** derleyici seçeneğini ayarlayın.

Bu uyarı, Visual Studio 2015 ' de yenidir ve varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

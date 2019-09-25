---
title: Derleyici Uyarısı C4577
description: Derleyici Uyarısı C4577 açıklaması ve çözümü.
ms.date: 09/18/2019
helpviewer_keywords:
- C4577
ms.openlocfilehash: 637023f4c27f93238fbbd13b4a0e652e6cd958e0
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71241103"
---
# <a name="compiler-warning-level-1-c4577"></a>Derleyici Uyarısı (düzey 1) C4577

> ' noexcept ', özel durum işleme modu belirtilmediği için kullanıldı; özel durum üzerinde sonlandırma garanti edilmez. /EHsc belirtin

Derleyici bir `noexcept` belirtim algıladı, ancak standart C++ özel durum işleme belirtilmedi. Derleyici, C++ [/EHsc](../../build/reference/eh-exception-handling-model.md) derleyici seçeneği belirtilmediği takdirde standart olarak özel durum işlemesini tam olarak desteklemez. Bu sorunu çözmek için **/EHsc** derleyici seçeneğini ayarlayın.

Bu uyarı, Visual Studio 2015 ' de yenidir ve varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

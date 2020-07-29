---
title: Derleyici Uyarısı C4577
description: Derleyici Uyarısı C4577 açıklaması ve çözümü.
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: fb9d412196e7764326a397a4bf6e76c8723ac2ae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196259"
---
# <a name="compiler-warning-level-1-c4577"></a>Derleyici Uyarısı (düzey 1) C4577

> ' noexcept ', özel durum işleme modu belirtilmediği için kullanıldı; özel durum üzerinde sonlandırma garanti edilmez. /EHsc belirtin

Derleyici bir belirtim algıladı **`noexcept`** , ancak standart C++ özel durum işleme belirtilmedi. Derleyici, [/EHsc](../../build/reference/eh-exception-handling-model.md) derleyici seçeneği belirtilmediği takdirde C++ standardına göre özel durum işlemeyi tam olarak desteklemez. Bu sorunu çözmek için **/EHsc** derleyici seçeneğini ayarlayın.

Bu uyarı, Visual Studio 2015 ' de yenidir ve varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

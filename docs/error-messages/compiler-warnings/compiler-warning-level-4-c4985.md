---
title: Derleyici Uyarısı (düzey 4) C4985
ms.date: 11/04/2016
f1_keywords:
- C4985
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: 87537e960c858cc6741108cf191fbeb2a7a2a8d7
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87390019"
---
# <a name="compiler-warning-level-4-c4985"></a>Derleyici Uyarısı (düzey 4) C4985

> '*sembol-adı*': öznitelikler önceki bildirimde yok.

Geçerli yöntem bildiriminde veya tanımında bulunan Microsoft kaynak kodu ek açıklama dili (SAL) ek açıklamaları, önceki bir bildirimin ek açıklamalarından farklıdır. Bir yöntemin tanımında ve bildirimlerinde aynı SAL ek açıklamaları kullanılmalıdır.

SAL, bir işlevin parametrelerini nasıl kullandığını, bunların ilgili olduğu varsayımları ve tamamlanmakta olduğu garantisi sağlamak için kullanabileceğiniz bir dizi ek açıklama sağlar. Ek açıklamalar Sal. h üstbilgi dosyasında tanımlanmıştır.

Proje belirtilen bayrak içermiyorsa SAL makrolarının genişlemeyeceğini unutmayın [`/analyze`](../../build/reference/analyze-code-analysis.md) . Belirttiğinizde **`/analyze`** , hiçbir uyarı veya hata olmadan görüntülenmese bile derleyici C4985 oluşturabilir **`/analyze`** .

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Bir yöntemin tanımında ve tüm bildirimlerinde aynı SAL ek açıklamalarını kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[SAL ek açıklamaları](../../c-runtime-library/sal-annotations.md)

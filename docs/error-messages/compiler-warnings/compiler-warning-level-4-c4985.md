---
title: Derleyici Uyarısı (düzey 4) C4985
ms.date: 11/04/2016
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: 6f098b25848d4fca0431663bd61ad71646c8d644
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661077"
---
# <a name="compiler-warning-level-4-c4985"></a>Derleyici Uyarısı (düzey 4) C4985

'sembol name': öznitelikler önceki bildirimde yok.

Microsoft kaynak kodu ek açıklama dili (SAL) ek açıklamalar geçerli yöntemi bildirim veya tanımdan ek açıklamalar önceki bir bildirimde farklıdır. Aynı SAL ek açıklamaları tanım ve bildirimleri yöntemin kullanılması gerekir.

SAL ek açıklamaları nasıl bir işlev parametrelerini ve bunlar hakkında kolaylaştırır varsayımların kolaylaştırır garanti tamamlama üzerinde kullandığını tanımlamak için kullanabileceğiniz bir dizi sağlar. Ek açıklamalar sal.h üstbilgi dosyasında tanımlanır.

Proje sahip olmadığı sürece SAL makroları genişletilemez dikkat edin [/ analyze](../../build/reference/analyze-code-analysis.md) bayrağı belirtilmiş. Belirttiğinizde **/ analyze**, uyarı veya hata olmadan görünen olsa bile derleyici C4985, oluşturabilecek **/ analyze**.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Aynı SAL ek açıklamalarını tanımında bir yöntem ve tüm bildirimleri kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)
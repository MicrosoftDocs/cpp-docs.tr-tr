---
title: Derleyici Uyarısı (düzey 4) C4985
ms.date: 11/04/2016
f1_keywords:
- C4985
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: 82adb80310fb43c848c253f9bf5e436c8c379f35
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198101"
---
# <a name="compiler-warning-level-4-c4985"></a>Derleyici Uyarısı (düzey 4) C4985

' sembol adı ': önceki bildirimde öznitelikler yok.

Geçerli yöntem bildiriminde veya tanımında bulunan Microsoft kaynak kodu ek açıklama dili (SAL) ek açıklamaları, önceki bir bildirimin ek açıklamalarından farklıdır. Bir yöntemin tanımında ve bildirimlerinde aynı SAL ek açıklamaları kullanılmalıdır.

SAL, bir işlevin parametrelerini nasıl kullandığını, bunların ilgili olduğu varsayımları ve tamamlanmakta olduğu garantisi sağlamak için kullanabileceğiniz bir dizi ek açıklama sağlar. Ek açıklamalar Sal. h üstbilgi dosyasında tanımlanmıştır.

Proje [/Analyze](../../build/reference/analyze-code-analysis.md) bayrağını belirtmediği takdirde Sal makrolarının genişlemeyeceğini unutmayın. **/Analyze**belirttiğinizde, hiçbir uyarı veya hata, **/Analyze**olmadan görünmese bile derleyici C4985 oluşturabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Bir yöntemin tanımında ve tüm bildirimlerinde aynı SAL ek açıklamalarını kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)

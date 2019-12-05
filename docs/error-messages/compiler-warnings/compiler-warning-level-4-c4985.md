---
title: Derleyici Uyarısı (düzey 4) C4985
ms.date: 11/04/2016
f1_keywords:
- C4985
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: 75feda6fb2c88b663aa6ade0efdfffc7def1568f
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810724"
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
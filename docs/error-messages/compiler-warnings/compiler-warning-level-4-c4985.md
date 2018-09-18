---
title: Derleyici Uyarısı (düzey 4) C4985 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d67b7394ef9bd38409ca45abe6ed7d347f5a37d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092679"
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
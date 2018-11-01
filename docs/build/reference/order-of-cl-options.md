---
title: CL Seçenekleri Sırası
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: e5dd07f52f853b17bf663e2fbad7dbe66a3a1db7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633547"
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası

Seçenekleri, CL komut satırında son gerçekleşmelidir/Link seçeneği dışında herhangi bir yerde görünebilir. Belirtilen seçeneklerle derleyici başlar [CL ortam değişkeninde](../../build/reference/cl-environment-variables.md) ve komut satırı soldan sağa okur; bunları bulduğu sırada komut dosyaları işleme. Her seçeneğin komut satırında tüm dosyalar için geçerlidir. CL çakışan seçenekler karşılaşırsa, en sağdaki seçeneğini kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)